# 📖 Lecture 1: Review of First-Order Logic

> **Foundation review - what you should already know**

---

## 📅 Lecture Info

| Item | Details |
|------|---------||
| **Week** | 1-2 |
| **Slides** | ✅ [1-first-order-logic.pdf](./1-first-order-logic.pdf) |
| **Textbook** | Prerequisite material (review) |
| **Status** | ⬜ Not yet attended |

---

## ✅ Pre-Lecture Checklist

- [x] Slides downloaded ✅
- [ ] Skimmed slides before lecture
- [ ] Reviewed FOL from previous courses

## ✅ Post-Lecture Checklist

- [ ] Attended lecture
- [ ] Reviewed notes same day
- [ ] Completed key concepts below
- [ ] Self-assessed prerequisite knowledge
- [ ] Wrote M&M reflection

---

## 📋 Lecture Overview

**Source:** `1-first-order-logic.pdf`  
**Total Slides:** 41  
**Textbook:** Prerequisite review material

### 📑 Lecture Outline (6 Sections)

| # | Section | Slides | Key Focus |
|---|---------|--------|----------|
| 1 | What is First-Order Logic? | 3-8 | Logic fundamentals, predicate logic |
| 2 | First-Order Structures | 9-12 | Mathematical structures, domains |
| 3 | FOL: Syntax | 13-24 | Symbols, terms, formulas, substitution |
| 4 | FOL: Semantics | 25-30 | Models, satisfaction, validity |
| 5 | FOL: Theories | 31-36 | Axioms, examples (monoids, PA) |
| 6 | Observations | 37-40 | FOL shortcomings → Alonzo |

---

## 🎯 Learning Objectives

After this lecture, you should:
- [ ] Explain what logic is (study of sound reasoning, truth, logical consequence)
- [ ] Distinguish: syntax vs semantics, language vs metalanguage, theory vs model
- [ ] Define first-order structures as $(\{D\}, A)$ with members, functions, predicates
- [ ] Write FOL terms and formulas using formation rules
- [ ] Compute free/bound variables and perform substitutions
- [ ] Define models $M = (D, I)$ and valuation functions $V^M$
- [ ] Explain satisfiability, validity, and logical consequence
- [ ] Write theories as $(L, \Gamma)$ with language and axioms
- [ ] Identify FOL shortcomings that motivate STT/Alonzo

---

## 📝 Lecture Notes

---

### 1️⃣ What is First-Order Logic? (Slides 3-8)

**What is Logic?** (Slide 4)
- The study of principles underlying **sound reasoning**
- Central ideas: **truth** and **logical consequence**
- Branch of mathematics underlying mathematical reasoning and computation

**Fundamental Distinctions** (Slide 5)
| Distinction | Description |
|-------------|-------------|
| Syntax vs. Semantics | Form vs. meaning |
| Language vs. Metalanguage | Object language vs. language about it |
| Theory vs. Model | Abstract axioms vs. concrete interpretation |

**What is a Logic?** (Slide 6)
- Informally: A system of reasoning
- Formally: A family of formal languages with:
  1. A precise common **syntax**
  2. A precise common **semantics** with notion of logical consequence

**Predicate Logic** (Slide 7)
- Study of statements about **individuals** using:
  - Predicates, functions, Boolean operators, quantifiers

**First-Order Logic** (Slide 8)
- Leading form of predicate logic
- "First-order" = quantification over **individuals only**
- NOT over higher-order objects (sets, relations, functions, predicates)

---

### 2️⃣ First-Order Structures (Slides 9-12)

**Mathematical Structures** (Slide 10)
- A set of mathematical values with structure via distinguished values
- Examples: Number systems, orders, equivalence relations, algebraic structures

**First-Order Structure Definition** (Slide 12)
$$\text{A first-order structure is } (\{D\}, A) \text{ where each } a \in A \text{ is:}$$
1. A member of $D$
2. A function over $D$, or
3. A predicate over $D$

---

### 3️⃣ FOL: Syntax (Slides 13-24)

**Symbols** (Slide 14)
| Symbol Set | Description |
|------------|-------------|
| $S_{var}$ | Variable symbols |
| $S_{con}$ | Individual constant symbols |
| $S^n_{fun}$ | n-ary function symbols |
| $S^n_{pred}$ | n-ary predicate symbols |

**Terms** (Slide 15) - Defined inductively:
1. **Variable:** If $x \in S_{var}$, then $x$ is a term
2. **Constant:** If $c \in S_{con}$, then $c$ is a term
3. **Function application:** If $f \in S^n_{fun}$ and $t_1,...,t_n$ are terms, then $f(t_1,...,t_n)$ is a term

**Formulas** (Slide 16) - Defined inductively:
1. **Equality:** $(t_1 = t_2)$ is a formula
2. **Predicate:** $P(t_1,...,t_n)$ is a formula  
3. **Negation:** $\neg A$ is a formula
4. **Implication:** $(A \Rightarrow B)$ is a formula
5. **Universal:** $(\forall x. A)$ is a formula

**Notational Definitions** (Slide 17)
| Notation | Stands for |
|----------|------------|
| $s \neq t$ | $\neg(s = t)$ |
| $\top$ | $\forall x.(x = x)$ |
| $\bot$ | $\neg\top$ |
| $A \lor B$ | $(\neg A) \Rightarrow B$ |

**Bound and Free Variables** (Slides 19-21)
- Variable $x$ is **free** in term $t$ if it occurs in $t$
- Occurrence of $x$ in formula $A$ is **bound** if within $\forall x. B$
- $fvar(t)$ = set of free variables in $t$
- $bvar(A)$ = set of bound variables in $A$

**Substitution** (Slides 22-23)
- $s[x \mapsto t]$ = result of substituting $t$ for $x$ in $s$

**Languages** (Slide 24)
- A language $L = (C, F, P)$ where:
  - $C \subseteq S_{con}$
  - $F \subseteq \bigcup S^n_{fun}$
  - $P \subseteq \bigcup S^n_{pred}$

---

### 4️⃣ FOL: Semantics (Slides 25-30)

**Model Definition** (Slide 26)
$$M = (D, I) \text{ where:}$$
- $D$ = nonempty domain
- $I$ = interpretation function:
  - $I(c) \in D$ for constants
  - $I(f): D^n \to D$ for n-ary functions
  - $I(P) \subseteq D^n$ for n-ary predicates

**Valuation Function** (Slides 27-28)
- $V^M_\phi(t)$ = value of term $t$ under assignment $\phi$
- $V^M_\phi(A) \in \{t, f\}$ = truth value of formula $A$

**Key Semantic Concepts** (Slide 29)
| Concept | Definition |
|---------|------------|
| **Satisfiable** | $V^M_\phi(A) = t$ for some $M, \phi$ |
| **Valid** | $V^M_\phi(A) = t$ for all $M, \phi$ |
| **Logical consequence** | $\Gamma \models A$ |

**Quantifier Notes** (Slide 30)
- $\neg(\forall x. A) \equiv \exists x. \neg A$
- $\neg(\exists x. A) \equiv \forall x. \neg A$
- Order of quantifiers matters!

---

### 5️⃣ FOL: Theories (Slides 31-36)

**Theory Definition** (Slide 32)
$$T = (L, \Gamma) \text{ where:}$$
- $L$ = language of FOL
- $\Gamma$ = set of sentences (axioms)

**Example: Strong Partial Orders** (Slide 33)
- Language: $L = (\emptyset, \emptyset, \{<\})$
- Axioms:
  1. $\forall x. \neg(x < x)$ (irreflexive)
  2. $\forall x,y,z. (x < y \land y < z) \Rightarrow x < z$ (transitive)

**Example: Monoids** (Slide 34)
- Language: $L = (\{e\}, \{*\}, \emptyset)$
- Axioms:
  1. $\forall x,y,z. (x*y)*z = x*(y*z)$ (associativity)
  2. $\forall x. e*x = x \land x*e = x$ (identity)

**Example: Peano Arithmetic** (Slide 35)
- Language: $L = (\{0\}, \{S, +, \cdot\}, \emptyset)$
- Axioms include successor, addition, multiplication, induction

**Theory vs. Model** (Slide 36)
- **Model:** Concrete interpretation of expressions as values
- **Theory:** Abstract mathematical model consisting of sentences

---

### 6️⃣ Observations (Slides 37-40)

**Variants of FOL** (Slide 38)
- FOL without function symbols (FOLwoFS)
  - Same theoretical expressivity, lower practical expressivity
  - Less complex, same logical principles

**⚠️ Shortcomings of FOL** (Slide 39)
| Limitation | Problem |
|------------|----------|
| Only one base type | All individuals same type |
| Functions/predicates on individuals only | No higher-order |
| Quantifiers on individual variables only | Can't quantify over sets/functions |
| No undefined terms | Can't handle partial functions |

**🚀 Transforming FOL → Alonzo** (Slide 40)
1. Allow **higher-order** functions and predicates (STT)
2. Use **types** to organize different values (STT)
3. Combine terms and formulas into **expressions** (CTT)
4. Introduce **lambda notation** (CTT)
5. Introduce **definite description** (CTT)
6. Admit **undefined expressions** (Alonzo)

---

## 🔑 Key Concepts

| Term | Definition | Example |
|------|------------|---------|
| Term | | |
| Atomic Formula | | |
| Quantifier | | |
| Structure/Model | | |
| Interpretation | | |
| Satisfaction | | |
| Validity | | |
| Soundness | | |
| Completeness | | |

---

## 📊 Self-Assessment: FOL Prerequisites

Rate your understanding (1-5):

| Topic | Before Lecture | After Lecture |
|-------|----------------|---------------|
| FOL Syntax | /5 | /5 |
| FOL Semantics | /5 | /5 |
| FOL Proofs | /5 | /5 |
| Induction proofs | /5 | /5 |
| Set theory basics | /5 | /5 |

**Action items if any < 3:**
- 
- 

---

## ❓ Questions

1. 
2. 
3. 

---

## 🔗 Resources

- [Stanford Encyclopedia - FOL](https://plato.stanford.edu/entries/logic-classical/)
- Course slides (Avenue)
- Any undergraduate logic textbook

---

## 💭 M&M Reflection

```
(Draft your M&M here)




```

---

*Completed: ⬜ Yes / ⬜ No*
