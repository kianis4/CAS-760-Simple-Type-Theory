# 📖 Lecture 5: Proof Systems

> **How to prove theorems in Alonzo**

---

## 📅 Lecture Info

| Item | Details |
|------|---------||
| **Week** | 6-7 |
| **Slides** | ✅ [5-proof-systems.pdf](./5-proof-systems.pdf) |
| **Textbook** | Chapter 8, Appendices A-C |
| **Status** | ⬜ Not yet attended |

---

## ✅ Pre-Lecture Checklist

- [x] Slides downloaded ✅
- [ ] Skimmed slides before lecture
- [ ] Read Chapter 8 of STT textbook
- [ ] Read Appendices A, B, C

## ✅ Post-Lecture Checklist

- [ ] Attended lecture
- [ ] Reviewed notes same day
- [ ] Practice proof exercises
- [ ] Wrote M&M reflection

---

## 📋 Lecture Overview

**Source:** `5-proof-systems.pdf`  
**Total Slides:** 18  
**Textbook:** STT Chapter 8, Appendices A-C

### 📑 Lecture Outline (3 Sections)

| # | Section | Slides | Key Focus |
|---|---------|--------|----------|
| 1 | Background | 3-7 | Proofs, theorems, soundness/completeness |
| 2 | A Proof System for Alonzo | 8-13 | System 𝒜, axioms A1-A6, rules R1-R2 |
| 3 | Soundness and Completeness | 14-17 | Theorems, frugal models, completeness |

---

## 🎯 Learning Objectives

**Knowledge:**
- [ ] Define what a proof system consists of (axioms + rules of inference)
- [ ] Explain proofs as sequences of formulas derived from axioms
- [ ] Define soundness: $\vdash_P A$ implies $\models A$
- [ ] Define completeness: $\models A$ implies $\vdash_P A$
- [ ] State Henkin's theorem on incompleteness for standard semantics
- [ ] List axioms A1-A6 of system 𝒜 (Truth, Leibniz, Extensionality, etc.)
- [ ] List rules R1 (Modus Ponens) and R2 (Quasi-Equality Substitution)
- [ ] Define frugal models and their role in completeness

**Skills:**
- [ ] Construct proofs in system 𝒜
- [ ] Apply axioms correctly with definedness conditions

---

## 📝 Lecture Notes

---

### 1️⃣ Background (Slides 3-7)

**Proofs and Theorems** (Slide 4)

> A **proof system** $P$ for Alonzo consists of:
> 1. A **decidable set of axioms**
> 2. A set of **rules of inference**

- A **proof** of $A_o$ in $P$ is a finite sequence of formulas ending in $A_o$
- Each formula is either an axiom or derived by a rule from earlier formulas
- $A_o$ is a **theorem** of $P$ (written $\vdash_P A_o$) if there is a proof of $A_o$ in $P$

**Proofs from Premises** (Slide 5)
- Let $\Gamma$ be a set of formulas (premises/hypotheses)
- A **proof of $A_o$ from $\Gamma$** in $P$ is a pair $(\Gamma', \pi)$ where:
  - $\Gamma' \subseteq \Gamma$ is finite
  - $\pi$ is a proof of $A_o$ using axioms + formulas from $\Gamma'$
- Written: $\Gamma \vdash_P A_o$

**Soundness and Completeness** (Slide 6)

| Property | Definition | Meaning |
|----------|------------|--------|
| **Sound** | $\vdash_P A_o \Rightarrow \models A_o$ | Provable implies valid |
| **Complete** | $\models A_o \Rightarrow \vdash_P A_o$ | Valid implies provable |

**⚠️ Henkin's Theorem** (Slide 7)
> **Theorem:** There is NO sound proof system for Alonzo that is complete in the **standard** sense.

- Completeness is only possible w.r.t. **general models**
- This is why we need general semantics!

---

### 2️⃣ A Proof System for Alonzo: System 𝒜 (Slides 8-13)

**System 𝒜** (named for Peter Andrews)

#### Axioms A1-A6

| Axiom | Name | Statement |
|-------|------|----------|
| **A1** | Truth | $T_o$ |
| **A2** | Leibniz | $(A_\alpha = B_\alpha) \Rightarrow (F_{\alpha \to o}\, A \Rightarrow F\, B)$ |
| **A3** | Extensionality | $(\forall x : \alpha . F\, x = G\, x) \Rightarrow (F = G)$ |
| **A4** | Beta-Reduction | $A \downarrow \Rightarrow (\lambda x : \alpha . B)\, A = B[x \mapsto A]$ |

**A5: Definedness Axioms** (Slide 10)
| # | Axiom |
|---|-------|
| A5.1 | $(x : \alpha) \downarrow$ (variables are defined) |
| A5.2 | $(c : \alpha) \downarrow$ (constants are defined) |
| A5.3 | $F\, A \downarrow \Rightarrow A \downarrow$ (application preserves definedness) |
| A5.4 | $(\lambda x : \alpha . B) \downarrow$ (abstractions are defined) |

**A6: Definite Description Axioms** (Slide 11)
| # | Axiom |
|---|-------|
| A6.1 | $(\exists! x : \alpha . A_o) \Rightarrow (I x : \alpha . A_o) \in \{x : \alpha \mid A_o\}$ |
| A6.2 | $\neg(\exists! x : \alpha . A_o) \Rightarrow (I x : \alpha . A_o) \uparrow$ |

#### Rules of Inference R1-R2 (Slide 12)

| Rule | Name | Statement |
|------|------|----------|
| **R1** | Modus Ponens | From $A_o$ and $A_o \Rightarrow B_o$, infer $B_o$ |
| **R2** | Quasi-Equality Substitution | From $A \simeq B$ and $C_o$, infer $C_o[A \mapsto B]$ |

**Proofs from Premises in 𝒜** (Slide 13)
- Same structure as before, but using axioms A1-A6 and rules R1-R2
- Premises act as additional assumptions

---

### 3️⃣ Soundness and Completeness (Slides 14-17)

**⭐ Soundness Theorem** (Slide 15)
> **Theorem:** System 𝒜 is **sound**.
> - Proof: Theorem B.11 in Appendix B

**Consistency Corollary:**
> 𝒜 is **consistent** (cannot prove both $A$ and $\neg A$)

**Frugal Models** (Slide 16)
- A general model $M$ of $L$ is **frugal** if $\|M\| \leq \|L\|$
- **Theorem:** Every frugal infinite general model of a language $L$ is a model of any consistent theory over $L$

**⭐ Completeness Theorems** (Slide 17)

> **Theorem (Provability = Validity):** System 𝒜 is sound and complete.
> $$\vdash_{\mathcal{A}} A_o \iff \models A_o$$

> **Theorem (Deduction):** 
> $$\Gamma \vdash_{\mathcal{A}} A_o \iff \Gamma \models A_o$$

**Note:** Completeness is w.r.t. **general models**, not standard models!

---

## 🔑 Key Concepts

| Term | Definition |
|------|------------|
| Proof system | Decidable axioms + rules of inference |
| Proof | Finite sequence deriving a formula |
| Theorem | Formula with a proof ($\vdash A$) |
| Soundness | Provable ⟹ Valid |
| Completeness | Valid ⟹ Provable |
| System 𝒜 | Andrews-style proof system for Alonzo |
| Frugal model | Model with $\|M\| \leq \|L\|$ |
| Modus Ponens | From $A$ and $A \Rightarrow B$, infer $B$ |

---

## ✏️ Practice Proofs

**Proof 1: Reflexivity of Equality**
```
Theorem: ⊢ ∀x:α. x = x

Proof sketch:
1. (λx:α. x) = (λx:α. x)     [A1, equality is reflexive for T]
2. Apply A3 (Extensionality)
```

**Proof 2: Using Modus Ponens**
```
Theorem: From A and A ⟹ B, derive B

Proof:
1. A                          [Premise]
2. A ⟹ B                      [Premise]  
3. B                          [R1: Modus Ponens on 1,2]
```

---

## 📚 Reading Notes

### Chapter 8: Key Points
- System 𝒜 has 6 axiom schemas and 2 rules
- Definedness conditions (A5) are crucial for handling undefined terms
- Definite description (A6) connects syntax to unique existence

### Appendix B: Soundness Proof
- Proves each axiom is valid
- Proves each rule preserves validity

---

## 💭 M&M Reflection

```




```

---

*Completed: ⬜ Yes / ⬜ No*
