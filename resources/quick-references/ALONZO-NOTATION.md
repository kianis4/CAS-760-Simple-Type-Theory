# 📐 Alonzo Notation Quick Reference

> **Common symbols and notation in Alonzo**

---

## Types

| Notation | Name | Meaning |
|----------|------|---------|
| ι | Iota | Type of individuals |
| ο | Omicron | Type of truth values (booleans) |
| α → β | Function type | Functions from α to β |
| α × β | Product type | Pairs of α and β |

---

## Expressions

| Notation | Name | Meaning |
|----------|------|---------|
| x_α | Typed variable | Variable x of type α |
| c_α | Typed constant | Constant c of type α |
| (F A) | Application | Apply F to A |
| λx_α . B | Abstraction | Function mapping x to B |
| ℩x_α . A | Definite description | The unique x such that A |

---

## Logical Connectives

| Symbol | Name | Type | Meaning |
|--------|------|------|---------|
| ⊤ | True | ο | Truth |
| ⊥ | False | ο | Falsity |
| ¬ | Not | ο → ο | Negation |
| ∧ | And | ο → ο → ο | Conjunction |
| ∨ | Or | ο → ο → ο | Disjunction |
| ⊃ | Implies | ο → ο → ο | Implication |
| ≡ | Iff | ο → ο → ο | Biconditional |

---

## Quantifiers

| Symbol | Name | Type | Meaning |
|--------|------|------|---------|
| ∀x_α . A | For all | (α → ο) → ο | Universal quantification |
| ∃x_α . A | Exists | (α → ο) → ο | Existential quantification |
| ∃!x_α . A | Unique | (α → ο) → ο | Unique existence |

---

## Equality and Definedness

| Symbol | Name | Meaning |
|--------|------|---------|
| A =_α B | Equality | A equals B (both of type α) |
| A ≠_α B | Inequality | A does not equal B |
| A↓ | Defined | A has a value |
| A↑ | Undefined | A has no value |
| A ≃ B | Quasi-equality | A = B or both undefined |

---

## Common Abbreviations

| Abbreviation | Expansion |
|--------------|-----------|
| A ⊃ B | ¬A ∨ B |
| A ≡ B | (A ⊃ B) ∧ (B ⊃ A) |
| ∃x.A | ¬∀x.¬A |
| ∃!x.A | ∃x.(A ∧ ∀y.(A[y/x] ⊃ y = x)) |

---

## LaTeX Commands (from LaTeX for Alonzo)

*Download the actual macros from Avenue. Common patterns:*

```latex
% Types
\iota         % ι
\omicron      % ο
\to           % →

% Logic
\top          % ⊤
\bot          % ⊥
\neg          % ¬
\land         % ∧
\lor          % ∨
\supset       % ⊃
\equiv        % ≡

% Quantifiers
\forall       % ∀
\exists       % ∃

% Lambda
\lambda       % λ

% Definite description
\iota         % ℩ (may need custom command)

% Definedness
\downarrow    % ↓ (defined)
\uparrow      % ↑ (undefined)
```

---

## Type Inference Rules

```
Γ ⊢ x : α        (if x:α ∈ Γ)      [Variable]

Γ ⊢ F : α → β    Γ ⊢ A : α
─────────────────────────────      [Application]
        Γ ⊢ (F A) : β

Γ, x:α ⊢ B : β
─────────────────────────────      [Abstraction]
   Γ ⊢ (λx_α . B) : α → β
```

---

## Proof Rules Summary

### Introduction Rules

| Connective | Rule |
|------------|------|
| ∧ | From A and B, conclude A ∧ B |
| ∨ | From A (or B), conclude A ∨ B |
| ⊃ | Assume A, prove B, conclude A ⊃ B |
| ∀ | Prove A[x] for arbitrary x, conclude ∀x.A |
| ∃ | From A[t] for some term t, conclude ∃x.A |

### Elimination Rules

| Connective | Rule |
|------------|------|
| ∧ | From A ∧ B, conclude A (or B) |
| ∨ | From A ∨ B, A⊃C, B⊃C, conclude C |
| ⊃ | From A ⊃ B and A, conclude B (Modus Ponens) |
| ∀ | From ∀x.A, conclude A[t] for any term t |
| ∃ | From ∃x.A and A[x]⊃C (x not in C), conclude C |

---

*Keep this reference handy when working on assignments!*
