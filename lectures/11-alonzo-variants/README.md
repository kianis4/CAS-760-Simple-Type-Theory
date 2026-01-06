# 📖 Lecture 11: Alonzo Variants

> **Exploring variations of Alonzo**

---

## 📅 Lecture Info

| Item | Details |
|------|---------||
| **Week** | 11-12 |
| **Slides** | ✅ [11-alonzo-variants.pdf](./11-alonzo-variants.pdf) |
| **Textbook** | Chapter 15 |
| **Status** | ⬜ Not yet attended |

---

## ✅ Pre-Lecture Checklist

- [x] Slides downloaded ✅
- [ ] Skimmed slides before lecture
- [ ] Read Chapter 15 of STT textbook

## ✅ Post-Lecture Checklist

- [ ] Attended lecture
- [ ] Reviewed notes same day
- [ ] Wrote M&M reflection

---

## 📋 Lecture Overview

**Source:** `11-alonzo-variants.pdf`  
**Total Slides:** 32  
**Textbook:** STT Chapter 15

### 📑 Lecture Outline (3 Sections)

| # | Section | Slides | Key Focus |
|---|---------|--------|----------|
| 1 | AlonzoID: Indefinite Description | 3-6 | Choice function, ℐ operator, theorems |
| 2 | AlonzoS: Sorts | 7-22 | Subtypes, sort systems, ξ mapping, proof system |
| 3 | AlonzoQE: Quotation & Evaluation | 23-31 | Syntax-semantics interplay, ⌜A⌝, eval |

---

## 🎯 Learning Objectives

**AlonzoID (Indefinite Description):**
- [ ] State the formation rule for indefinite description $\mathcal{I}x : \alpha . A_o$
- [ ] Explain how the choice function affects valuation
- [ ] Apply theorems about indefinite descriptions

**AlonzoS (Sorts):**
- [ ] Explain why quasitypes are limited and what sorts add
- [ ] Define **sort system** $S = (B, A, \xi)$
- [ ] Explain the $\xi$ mapping from sorts to underlying types
- [ ] Use formation rules for sort expressions
- [ ] Describe frame and interpretation for AlonzoS

**AlonzoQE (Quotation & Evaluation):**
- [ ] Explain what quotation/evaluation add to the logic
- [ ] Use the quotation operator $\ulcorner A \urcorner$
- [ ] Use the evaluation operator for syntax-semantics reasoning
- [ ] State the disquotation theorem

---

## 📝 Lecture Notes

---

### 1️⃣ AlonzoID: Indefinite Description (Slides 3-6)

**Motivation:**
> Add indefinite description to Alonzo to obtain **AlonzoID**.
> Allows selecting an arbitrary element satisfying a predicate.

**New Formation Rule** (Slide 4)
> If $A_o$ is a formula and $x$ is a variable of type $\alpha \neq o$:
> $$\mathcal{I}x : \alpha . A_o$$
> is an expression of type $\alpha$.

**Reading:** "some $x$ of type $\alpha$ such that $A_o$"

**Semantic Condition** (Slide 5)
> A new condition is added to general models:
> $$V^M_\varphi(\mathcal{I}x : \alpha . A_o) = f(D_\alpha)$$
> where $f$ is a **choice function** selecting an element from $D_\alpha$.

| Case | Value |
|------|-------|
| Some $x$ satisfies $A_o$ | One such $x$ (chosen by $f$) |
| No $x$ satisfies $A_o$ | Arbitrary element from $D_\alpha$ |

**Key Theorem** (Slide 6)
> **Proposition:** The following formula is valid for all $\alpha \neq o$:
> $$\mathcal{I}x : \alpha . A_o \simeq x : \alpha . (A_o \land \exists! x : \alpha . A_o)$$

*When there's exactly one witness, indefinite description equals definite description.*

---

### 2️⃣ AlonzoS: Alonzo with Sorts (Slides 7-22)

**Why Sorts?** (Slides 7-9)

| Feature | Quasitypes | Sorts |
|---------|------------|-------|
| Restrict bound variables | ✅ | ✅ |
| Sharpen definedness | ✅ | ✅ |
| Interchangeable with types | ❌ | ✅ |
| Subtyping | ❌ | ✅ |
| Function/product sorts | ❌ | ✅ |

**Sort Formation** (Slides 9, 11)
> If $\sigma$ and $\tau$ are sorts with underlying types $\alpha$ and $\beta$:

| Sort | Underlying Type | Meaning |
|------|----------------|--------|
| $o$ (BoolTy) | $o$ | Truth values |
| $a$ (BaseTy) | $a$ | Base type |
| $\sigma \to \tau$ | $\alpha \to \beta$ | Function sort |
| $\sigma \times \tau$ | $\alpha \times \beta$ | Product sort |

**Sort Systems** (Slides 12-13)
> A **sort system** of AlonzoS is a tuple $S = (B, A, \xi)$ where:

| Component | Description |
|-----------|-------------|
| $B$ | Finite set of base types |
| $A$ | Finite set of atomic sorts |
| $\xi$ | Function mapping each sort in $A$ to its underlying type |

**The $\xi$ Mapping** (Slide 13)
> Extend $\xi$ canonically to all sorts:

| Sort $\sigma$ | $\xi(\sigma)$ |
|--------------|---------------|
| $o$ | $o$ |
| $a$ (base type) | $a$ |
| $s$ (atomic sort) | $\xi(s)$ |
| $\sigma \to \tau$ | $\xi(\sigma) \to \xi(\tau)$ |
| $\sigma \times \tau$ | $\xi(\sigma) \times \xi(\tau)$ |

**Expressions** (Slides 14-15)
> Formation rules for AlonzoS expressions:

| Rule | Form | Condition |
|------|------|-----------|
| E5 | $\lambda x : \sigma . B_\tau$ | Function abstraction |
| E6 | $\iota x : \sigma . A_o$ | Definite description, $\xi(\sigma) \neq o$ |

**Frames and Interpretations** (Slides 16-17)
> A **frame** for language $L = (S, C)$ is $D = \{D_\sigma \mid \sigma \in U(L)\}$ where:

| Condition | Requirement |
|-----------|-------------|
| F1 | $D_o = \mathbb{B} = \{f, t\}$ |
| F2 | $D_\sigma \subseteq D_{\xi(\sigma)}$ for atomic sorts |
| F3 | $D_{\sigma \to \tau} \subseteq D_{\xi(\sigma) \to \xi(\tau)}$ |

**General Models** (Slides 18-19)
> Valuation rules extend naturally with sort constraints:
> $$V^M_\varphi(F_{\sigma \to \tau} A_\sigma) = V^M_\varphi(F)(V^M_\varphi(A))$$
> when $V^M_\varphi(A) \in D_\sigma$.

**Notational Definitions** (Slide 20)
> Let $\alpha = \xi(\sigma) = \xi(\tau)$:

| Notation | Meaning |
|----------|--------|
| $A \downarrow_\sigma$ | $(\iota x : \sigma . T_o) A$ — definedness in sort |
| $A \uparrow_\sigma$ | $\neg(A \downarrow_\sigma)$ — undefined in sort |
| $\sigma \neq \emptyset$ | $\forall x : \sigma . x \downarrow$ — sort is nonempty |

**Proof System** (Slide 21)
> **PF** is a version of Church's type theory with:
> - Undefined expressions
> - Sorts
> - Sound and complete proof system

**Theorems** (Slide 22)
> Valid formulas in AlonzoS:
> 1. $A \downarrow_\sigma \Rightarrow A \downarrow_{\xi(\sigma)}$
> 2. Sort membership respects type membership

---

### 3️⃣ AlonzoQE: Quotation & Evaluation (Slides 23-31)

**Motivation** (Slides 24-25)
> Reason about the interplay of **syntax** and **semantics**.

| Concept | Description |
|---------|-------------|
| **SBMA** | Syntax-Based Mathematical Algorithm |
| **Quotation** | Refer to syntactic structure of expression |
| **Evaluation** | Refer to semantic value of expression |

**New Type** (Slide 26)
> **T5.** ExprTy ($\epsilon$) — type of expressions (syntax trees)

**New Formation Rules** (Slide 26)

| Rule | Form | Type | Description |
|------|------|------|-------------|
| E8 | $\ulcorner A_\alpha \urcorner$ | $\epsilon$ | Quotation of $A$ |
| E9 | $\llbracket E_\epsilon \rrbracket_\alpha$ | $\alpha$ | Evaluation of $E$ at type $\alpha$ |

**Logical Constants** (Slide 27)

| Constant | Type | Purpose |
|----------|------|---------|
| q-eq | $\epsilon \to \epsilon \to \epsilon$ | Quoted equality |
| q-app | $\epsilon \to \epsilon \to \epsilon$ | Quoted application |
| q-abs | $\epsilon \to \epsilon \to \epsilon$ | Quoted abstraction |

**Interpretation** (Slides 28-30)
> The function $\mu$ maps eval-free expressions to constructions:
> $$\mu(\lambda x : \alpha . B) = \ulcorner \lambda x : \alpha \urcorner$$

**Semantic Conditions** (Slide 30)
> New valuation rules:
> $$V^M_\varphi(\ulcorner A \urcorner) = \mu(A)$$
> $$V^M_\varphi(\llbracket E \rrbracket_\alpha) = \text{eval}(V^M_\varphi(E))$$

**Disquotation Theorem** (Slide 31)
> **Theorem:** Let $A$ be an eval-free expression, $M$ a general model, $\varphi$ an assignment. Then:
> $$\mu(V^M_\varphi(\ulcorner A \urcorner)) = A$$

*Evaluating a quotation returns the original expression.*

---

## 🔑 Key Concepts

| Term | Definition |
|------|------------|
| AlonzoID | Alonzo + indefinite description |
| $\mathcal{I}x : \alpha . A_o$ | "Some $x$ such that $A_o$" |
| Choice function | Selects element from domain |
| AlonzoS | Alonzo + sorts (subtypes) |
| Sort system | $(B, A, \xi)$ with base types, atomic sorts, mapping |
| $\xi(\sigma)$ | Underlying type of sort $\sigma$ |
| AlonzoQE | Alonzo + quotation/evaluation |
| $\ulcorner A \urcorner$ | Quotation: syntax tree of $A$ |
| $\llbracket E \rrbracket_\alpha$ | Evaluation: semantic value of $E$ |
| Disquotation | $\text{eval}(\ulcorner A \urcorner) = A$ |

---

## 📚 Reading Notes: Chapter 15

**Key Takeaways:**
- **AlonzoID:** Adds indefinite description for "there exists" selections
- **AlonzoS:** Adds sorts for subtyping, more expressive than quasitypes
- **AlonzoQE:** Enables metaprogramming and reflection
- Each variant is a **conservative extension** of base Alonzo
- Trade-offs: expressiveness vs complexity

---

## 💭 M&M Reflection

```




```

---

*Completed: ⬜ Yes / ⬜ No*
