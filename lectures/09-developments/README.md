# 📖 Lecture 9: Developments

> **Building mathematical knowledge systematically**

---

## 📅 Lecture Info

| Item | Details |
|------|---------||
| **Week** | 10 |
| **Slides** | ✅ [9-developments.pdf](./9-developments.pdf) |
| **Textbook** | Chapters 12-13 |
| **Status** | ⬜ Not yet attended |

---

## ✅ Pre-Lecture Checklist

- [x] Slides downloaded ✅
- [ ] Skimmed slides before lecture
- [ ] Read Chapters 12-13 of STT textbook

## ✅ Post-Lecture Checklist

- [ ] Attended lecture
- [ ] Reviewed notes same day
- [ ] Practice exercises
- [ ] Wrote M&M reflection

---

## 📋 Lecture Overview

**Source:** `9-developments.pdf`  
**Total Slides:** 23  
**Textbook:** STT Chapters 12-13

### 📑 Lecture Outline (3 Sections)

| # | Section | Slides | Key Focus |
|---|---------|--------|----------|
| 1 | Theory Developments | 3-11 | Building libraries, definition/theorem packages, extensions |
| 2 | Example: Peano Arithmetic | 12-13 | PA development series |
| 3 | Example: Real Number Mathematics | 14-22 | COF theory, REAL development, Skolem's paradox |

---

## 🎯 Learning Objectives

**Knowledge:**
- [ ] Explain how to build a mathematics library in Alonzo
- [ ] Define **definition packages** $(n, c, A, \delta)$
- [ ] Define **theorem packages** $(n, A_o, \pi)$
- [ ] Define **development** as pair $D = (T, \sigma)$ with theory and package sequence
- [ ] Explain trivial vs non-trivial developments
- [ ] Define **development extensions**
- [ ] Describe the structure of real number arithmetic $(\mathbb{R}, 0, 1, +, \cdot, -, ^{-1})$
- [ ] Write the Theory of Complete Ordered Fields (COF)
- [ ] Explain Skolem's Paradox for REAL

**Skills:**
- [ ] Build developments incrementally with packages
- [ ] Write development definition and extension modules

---

## 📝 Lecture Notes

---

### 1️⃣ Theory Developments (Slides 3-11)

**How to Build a Mathematics Library** (Slide 4)

> Build theories by:
> 1. **Defining new theories** (axiomatic foundations)
> 2. **Extending theories** (add types, constants, axioms)
> 3. **Developing theories** (add definitions and theorems)

**Definition Packages** (Slide 5)
> A **definition package** is a tuple $P = (n, c, A, \delta)$ where:

| Component | Description |
|-----------|-------------|
| $n$ | Name of the package |
| $c$ | New constant being defined |
| $A$ | Defining expression |
| $\delta$ | Proof that definition is valid |

**Example:** Define $1 := S(0)$ in PA
```
Package: ONE
Constant: 1 : N
Definition: 1 = S(0)
Proof: (trivial - definitional extension)
```

**Theorem Packages** (Slide 6)
> A **theorem package** is a tuple $P = (n, A_o, \pi)$ where:

| Component | Description |
|-----------|-------------|
| $n$ | Name of the theorem |
| $A_o$ | Statement (formula) |
| $\pi$ | Proof of $A_o$ |

**Example:** Prove $0 + 1 = 1$ in PA
```
Package: ZERO-PLUS-ONE
Theorem: 0 + 1 = 1
Proof: By definition of + and 1
```

**Developments** (Slides 7-8)
> A **theory development** (or development) of Alonzo is a pair:
> $$D = (T, \sigma)$$
> where:
> - $T$ is a theory
> - $\sigma = [P_1, P_2, ..., P_n]$ is a sequence of packages

**Key Properties:**
- $D$ is **trivial** if $\sigma = [\,]$ (empty sequence)
- Each package extends the theory: $T_0 \to T_1 \to ... \to T_n$
- Final theory: $T_n$ includes all definitions and theorems

**Development Definition Module** (Slide 9)
```
Development Definition X.Y
  Name: NAME
  Base Theory: T
  Packages: [P₁, P₂, ..., Pₙ]
```

**Development Extensions** (Slide 10)
> Let $D_1 = (T, \sigma_1)$ and $D_2 = (T, \sigma_2)$ be developments of $T$.
>
> $D_2$ is an **extension** of $D_1$ (or $D_1$ is a **subdevelopment** of $D_2$) if:
> $$\sigma_1 \text{ is a prefix of } \sigma_2$$

**Development Extension Module** (Slide 11)
```
Development Extension X.Y
  Name: NAME
  Extends: D₁
  New Packages: [Pₖ₊₁, ..., Pₙ]
```

---

### 2️⃣ Example: Peano Arithmetic (Slides 12-13)

**Development of PA** (Slide 13)

> Define a development of PA as a series of extensions:

```
D₀ = (PA, [])                           -- Base theory
  ↓ add definition of 1
D₁ = (PA, [ONE])                        -- With 1 = S(0)
  ↓ add definition of 2  
D₂ = (PA, [ONE, TWO])                   -- With 2 = S(1)
  ↓ add theorem
D₃ = (PA, [ONE, TWO, ONE-PLUS-ONE])     -- With 1 + 1 = 2
  ↓ ...
```

**Structure:**
```
PA
├── ONE: 1 = S(0)
├── TWO: 2 = S(S(0))
├── ONE-PLUS-ONE: 1 + 1 = 2
├── COMM-ADD: ∀x,y. x + y = y + x
└── ... (more definitions and theorems)
```

---

### 3️⃣ Example: Real Number Mathematics (Slides 14-22)

**Structure of Real Number Arithmetic** (Slide 15)
$$(\mathbb{R}, 0, 1, +, \cdot, -, ^{-1})$$

- One of the most important structures in mathematics
- Complete ordered field
- Foundation for analysis, calculus, physics

**Theory of Complete Ordered Fields (COF)** (Slides 16-18)
```
Name: COF
Language: L = ({R}, {0, 1 : R, + : R→R→R, · : R→R→R, 
                     - : R→R, ⁻¹ : R→R, pos : R→o})
```

**Axioms of COF:**

| # | Axiom | Name |
|---|-------|------|
| 1 | $\forall x,y,z : R. (x+y)+z = x+(y+z)$ | + associative |
| 2 | $\forall x,y : R. x+y = y+x$ | + commutative |
| 3 | $\forall x : R. x+0 = x$ | + identity |
| 4 | $\forall x : R. x+(-x) = 0$ | + inverse |
| 5 | $\forall x,y,z : R. (x \cdot y) \cdot z = x \cdot (y \cdot z)$ | · associative |
| 6 | $\forall x,y : R. x \cdot y = y \cdot x$ | · commutative |
| 7 | $\forall x : R. x \cdot 1 = x$ | · identity |
| 8 | $\forall x : R. x \neq 0 \Rightarrow x \cdot x^{-1} = 1$ | · inverse |
| 9 | Distributivity | |
| 10 | Ordering axioms (pos) | |
| 11 | $0 \neq 1$ | Nontriviality |
| 12 | Completeness (least upper bound) | |

**Alternative Constructions** (Slide 19)
1. Different theory of complete ordered fields (single step)
2. Build from PA using Dedekind cuts
3. Build from PA using Cauchy sequences

**Development of COF** (Slide 20)
```
D₀ = (COF, [])                    -- Base COF theory
  ↓ add subtraction
D₁ = (COF, [SUB])                 -- a - b = a + (-b)
  ↓ add division
D₂ = (COF, [SUB, DIV])            -- a / b = a · b⁻¹
  ↓ add ordering shortcuts
D₃ = (COF, [SUB, DIV, LT, GT])    -- <, >, ≤, ≥
  ↓ ...
```

**Notational Definitions for REAL** (Slide 21)

| Notation | Definition |
|----------|------------|
| $A \subseteq_R$ | $R \to R \to A \to R$ |
| $x < y$ | $pos(y - x)$ |
| $x \leq y$ | $x < y \lor x = y$ |
| $\|x\|$ | $\text{if } x \geq 0 \text{ then } x \text{ else } -x$ |

**⚠️ Skolem's Paradox** (Slide 22)

> **Observation:** REAL is satisfiable, so REAL has a **frugal model** $M$.

| Fact | Implication |
|------|-------------|
| $M$ is **nonstandard** | Not isomorphic to actual $\mathbb{R}$ |
| $M$ is **countable** | Only countably many elements |
| Yet $M \models$ "$\mathbb{R}$ is uncountable" | Internal vs external cardinality |

**Paradox Resolution:**
- "Uncountable" is a statement *within* the model
- The model itself can be countable *externally*
- This is a feature of first-order/higher-order logic with general models

---

## 🔑 Key Concepts

| Term | Definition |
|------|------------|
| Definition package | $(n, c, A, \delta)$ - named definition with proof |
| Theorem package | $(n, A_o, \pi)$ - named theorem with proof |
| Development | $(T, \sigma)$ - theory + package sequence |
| Trivial development | Development with empty package sequence |
| Development extension | Adds more packages to existing development |
| COF | Theory of Complete Ordered Fields |
| Skolem's Paradox | Countable model satisfying "uncountable" |

---

## 📚 Reading Notes

### Chapter 12: Developments
- Developments organize mathematical knowledge incrementally
- Packages are the building blocks
- Extensions allow modular growth

### Chapter 13: Real Numbers
- COF axiomatizes the reals
- Multiple construction paths exist
- Skolem's paradox highlights model theory subtleties

---

## 💭 M&M Reflection

```




```

---

*Completed: ⬜ Yes / ⬜ No*
