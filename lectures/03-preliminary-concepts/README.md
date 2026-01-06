# 📖 Lecture 3: Preliminary Concepts

> **Building blocks for understanding Alonzo**

---

## 📅 Lecture Info

| Item | Details |
|------|---------||
| **Week** | 3-4 |
| **Slides** | ✅ [3-prelim-concepts.pdf](./3-prelim-concepts.pdf) |
| **Textbook** | Chapter 3 |
| **Status** | ⬜ Not yet attended |

---

## ✅ Pre-Lecture Checklist

- [x] Slides downloaded ✅
- [ ] Skimmed slides before lecture
- [ ] Read Chapter 3 of STT textbook

## ✅ Post-Lecture Checklist

- [ ] Attended lecture
- [ ] Reviewed notes same day
- [ ] Completed key concepts below
- [ ] Practice exercises
- [ ] Wrote M&M reflection

---

## 📋 Lecture Overview

**Source:** `3-prelim-concepts.pdf`  
**Total Slides:** 25  
**Textbook:** STT Chapter 3

### 📑 Lecture Outline (5 Sections)

| # | Section | Slides | Key Focus |
|---|---------|--------|----------|
| 1 | What is Mathematics? | 3-5 | Tetrapod model |
| 2 | Mathematical Values | 6-13 | Functions, lambda notation, n-ary functions |
| 3 | Binders | 14-15 | Variable binding operators |
| 4 | Undefinedness | 16-21 | Traditional approach, partial functions |
| 5 | Mathematical Structures | 22-24 | Domains, function spaces |

---

## 🎯 Learning Objectives

- [ ] Explain the Tetrapod Model (inference, computation, visualization, symbolization)
- [ ] Define mathematical values (concrete and abstract objects)
- [ ] Define equivalence relations (reflexive, symmetric, transitive)
- [ ] Write functions using lambda notation $\lambda x. E$
- [ ] Represent n-ary functions as unary functions (tupling vs currying)
- [ ] Explain what a binder is and give examples
- [ ] Define undefined expressions and the undefinedness problem
- [ ] Distinguish equality vs quasi-equality for partial functions
- [ ] List domain building operations (function space, power set, product, disjoint union)

---

## 📝 Lecture Notes

---

### 1️⃣ What is Mathematics? (Slides 3-5)

**Definition** (Slide 4)
- Mathematics is a process for understanding the **mathematical aspects of the world**

**🦎 Tetrapod Model** (Slide 5)

Mathematical models are explored by:

| Method | Example |
|--------|--------|
| **Inference** | Proving a conjecture |
| **Computation** | Calculating a value |
| **Visualization** | Drawing a graph |
| **Symbolization** | Writing a formula |

---

### 2️⃣ Mathematical Values (Slides 6-13)

**Mathematical Values** (Slide 7)
- A **mathematical value** (value for short) is any concrete or abstract object used in mathematics

**Equivalence Relations** (Slide 8)
- A binary relation on a set is an **equivalence relation** if it is:
  - **Reflexive:** $a \sim a$
  - **Symmetric:** $a \sim b \Rightarrow b \sim a$
  - **Transitive:** $a \sim b \land b \sim c \Rightarrow a \sim c$

**Unary Functions** (Slide 9)
- **Definition:** A function is a rule $f: I \to O$ that associates members of $I$ (inputs) with members of $O$ (outputs)

**Lambda Notation** (Slide 10)
- Lambda notation is a precise, convenient way to describe functions:
$$\lambda x. E$$
- Example: $\lambda x. x^2$ is the squaring function

**n-ary Functions** (Slide 11)
- For $n \geq 0$, an n-ary function is a rule:
$$f: I_1, ..., I_n \to O$$

**Representing n-ary as Unary** (Slides 12-13)

Two ways to represent an n-ary function as unary:

| Method | Representation | Example |
|--------|---------------|--------|
| **Tupling** | $f': I_1 \times I_2 \to O$ | $f'(a,b) = a^2 + b^2$ |
| **Currying** | $f'': I_1 \to (I_2 \to O)$ | $f''(a)(b) = a^2 + b^2$ |

**Example** (Slide 13): Let $f: \mathbb{R}, \mathbb{R} \to \mathbb{R}$ defined by $f(a,b) = a^2 + b^2$
- Tupled: $f' = \lambda p: \mathbb{R} \times \mathbb{R}. [fst(p)]^2 + [snd(p)]^2$
- Curried: $f'' = \lambda a: \mathbb{R}. \lambda b: \mathbb{R}. a^2 + b^2$

---

### 3️⃣ Binders (Slides 14-15)

**What is a Binder?** (Slide 15)
- A **binder** $B$ is a special operator applied to:
  - A variable $x$
  - A set $S$ of values
  - An expression $E$

**Examples of Binders:**
| Binder | Notation | Meaning |
|--------|----------|--------|
| Lambda | $\lambda x: S. E$ | Function abstraction |
| Universal | $\forall x: S. E$ | For all $x$ in $S$, $E$ holds |
| Existential | $\exists x: S. E$ | There exists $x$ in $S$ such that $E$ |
| Summation | $\sum_{x \in S} E$ | Sum of $E$ over all $x$ in $S$ |
| Set builder | $\{x \in S \mid E\}$ | Set of $x$ in $S$ satisfying $E$ |

---

### 4️⃣ Undefinedness (Slides 16-21)

**The Undefinedness Problem** (Slide 17)
- A mathematical expression is **undefined** if:
  - It has no prescribed meaning, OR
  - It denotes a nonexistent value
- Examples: $1/0$, $\sqrt{-1}$ (in $\mathbb{R}$), $\lim_{x \to \infty} \sin(x)$

**Approaches for Handling Undefinedness** (Slide 18)
1. Represent partial function $f$ as a predicate (graph of $f$)
2. Use a logic of partial functions
3. Traditional approach (see below)

**Traditional Approach** (Slides 19-20)
Based on three principles:
1. Expressions may be **undefined**
2. Undefined expressions can occur in **meaningful statements**
3. Formulas with undefined subexpressions may still have truth values

**Two Kinds of Equality:**
| Type | Notation | Meaning |
|------|----------|--------|
| **Equality** | $a = b$ | $a$ and $b$ are defined and equal |
| **Quasi-equality** | $a \simeq b$ | $a$ and $b$ are both undefined, or both defined and equal |

**Benefits of Traditional Approach** (Slide 21)
- Meaningful statements can involve undefined expressions:
$$\forall x \in \mathbb{R}. (0 \leq x) \Rightarrow (\sqrt{x})^2 = x$$

---

### 5️⃣ Mathematical Structures (Slides 22-24)

**Structure Definition** (Slide 23)
- A **mathematical structure** is a pair $S = (D, A)$ where:
  - $D$ = set of domains
  - $A$ = set of distinguished values (constants, functions, predicates)

**Domain Building Operations** (Slide 24)

| Operation | Notation | Description |
|-----------|----------|-------------|
| Function space | $A \to B$ | Set of partial/total functions from $A$ to $B$ |
| Power set | $\mathcal{P}(A)$ | Set of all subsets of $A$ |
| Product | $A \times B$ | Set of ordered pairs |
| Disjoint union | $A + B$ | Tagged union of $A$ and $B$ |

---

## 🔑 Key Concepts from Chapter 3

| Term | Definition |
|------|------------|
| Mathematical value | Any concrete or abstract object used in math |
| Lambda notation | $\lambda x. E$ - function abstraction |
| Currying | Representing n-ary function as nested unary functions |
| Binder | Operator that binds a variable in an expression |
| Undefined expression | Expression with no prescribed meaning or nonexistent value |
| Quasi-equality | $a \simeq b$ - both undefined or both defined and equal |
| Mathematical structure | Pair $(D, A)$ of domains and distinguished values |

---

## ✏️ Practice Exercises

1. Convert $f(x, y, z) = x + y \cdot z$ to curried form
2. Give an example of an undefined expression in calculus
3. Write the squaring function using lambda notation
4. Explain the difference between $a = b$ and $a \simeq b$

---

## 📚 Reading Notes: Chapter 3

**Main Points:**
- Mathematical values are the objects we reason about
- Lambda notation provides precise function definitions
- Undefinedness is handled via the traditional approach
- Structures organize domains with distinguished values

---

## 💭 M&M Reflection

```




```

---

*Completed: ⬜ Yes / ⬜ No*
