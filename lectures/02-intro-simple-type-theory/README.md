# 📖 Lecture 2: Introduction to Simple Type Theory

> **The core of the course begins here**

---

## 📅 Lecture Info

| Item | Details |
|------|---------||
| **Week** | 2-3 |
| **Slides** | ✅ [2-intro-to-stt.pdf](./2-intro-to-stt.pdf) |
| **Textbook** | Chapters 1-2 |
| **Status** | ⬜ Not yet attended |

---

## ✅ Pre-Lecture Checklist

- [x] Slides downloaded ✅
- [ ] Skimmed slides before lecture
- [ ] Read Chapters 1-2 of STT textbook

## ✅ Post-Lecture Checklist

- [ ] Attended lecture
- [ ] Reviewed notes same day
- [ ] Completed key concepts below
- [ ] Practice exercises
- [ ] Wrote M&M reflection

---

## 📋 Lecture Overview

**Source:** `2-intro-to-stt.pdf`  
**Total Slides:** 15  
**Textbook:** STT Chapters 1-2

### 📑 Lecture Outline (3 Sections)

| # | Section | Slides | Key Focus |
|---|---------|--------|----------|
| 1 | Simple Type Theory | 3-7 | What is STT, history, seven virtues |
| 2 | Church's Type Theory | 8-12 | CTT, proof assistants, Alonzo |
| 3 | Model Theory vs. Proof Theory | 13-14 | Semantic vs syntactic consequence |

---

## 🎯 Learning Objectives

**Knowledge:**
- [ ] Define STT as classical higher-order predicate logic with types
- [ ] Trace history: Russell (1908) → Principia → Church (1940) → Henkin → Andrews
- [ ] List the Seven Virtues of Simple Type Theory
- [ ] Explain who benefits from STT (engineers, mathematicians, CS researchers)
- [ ] Distinguish Church's Type Theory from simple type theory
- [ ] Name proof assistants based on CTT (HOL, HOL Light, IMPS, Isabelle/HOL)
- [ ] Explain what Alonzo is and how it differs from Q₀
- [ ] Contrast model-theoretic vs proof-theoretic approaches

**Skills:**
- [ ] Compare STT to alternatives (FOL, set theory, dependent type theory)
- [ ] Choose semantic vs syntactic argument for logical consequence

---

## 📝 Lecture Notes

---

### 1️⃣ Simple Type Theory (Slides 3-7)

**What is Simple Type Theory?** (Slide 4)
- **Definition:** STT is a classical **higher-order** version of predicate logic and a form of type theory
- Types are used to:
  - **Classify expressions** by value
  - **Control the formation** of expressions

**📜 History of Type Theory** (Slide 5)

| Year | Person | Contribution |
|------|--------|--------------|
| 1908 | Russell | Ramified theory of types |
| 1910-12 | Russell, Whitehead | *Principia Mathematica* |
| 1940 | Church | Simple theory of types (STT) |
| 1950 | Henkin | General models semantics |
| 1963 | Andrews | Q₀ version of Church's type theory |
| 2002-08 | Farmer | Alonzo |

**⭐ Seven Virtues of Simple Type Theory** (Slide 6)

| # | Virtue |
|---|--------|
| 1 | Simple and highly uniform **syntax** |
| 2 | Semantics based on small set of **well-established ideas** |
| 3 | (Continue from textbook...) |
| 4 | |
| 5 | |
| 6 | |
| 7 | |

**Who Needs STT?** (Slide 7)
- Engineers who need to read/write **precise specifications**
- Mathematicians working with **formal proofs**
- Computer scientists using **proof assistants**
- Anyone applying **mathematical logic**

---

### 2️⃣ Church's Type Theory (Slides 8-12)

**Church's Type Theory (CTT)** (Slide 9)
- Very **practical** version of STT introduced by Alonzo Church (1940)
- Key features:
  - Tailored for **reasoning with functions**
  - Includes **lambda notation**
  - Includes **definite description**
  - Has a type of **truth values**

**🖥️ Proof Assistants Based on CTT** (Slide 10)

| System | Developer(s) |
|--------|-------------|
| HOL | Gordon |
| HOL Light | Harrison |
| IMPS | Farmer, Guttman, Thayer |
| Isabelle/HOL | Paulson, Nipkow, Wenzel |
| PVS | Owre, Rushby, Shankar |
| TPTP/TH1 | Sutcliffe, Benzmuller |

**Alternatives to CTT** (Slide 11)

| Alternative | Comparison |
|-------------|------------|
| First-order logic | Comparable theoretical expressivity, much less practical expressivity |
| Set theory | More theoretical expressivity, less practical expressivity |
| Dependent type theory | Supports computation directly, more complex than CTT |

**🔷 Alonzo** (Slide 12)
- Version of Church's type theory
- Named in honor of **Alonzo Church**
- Inspired by **Q₀** (Andrews' version of CTT)
- **How Alonzo differs from Q₀:**
  - (Fill in from textbook/slides)

---

### 3️⃣ Model Theory vs. Proof Theory (Slides 13-14)

**Two Ways to Prove Logical Consequence** (Slide 14)

> To prove $B$ is a logical consequence of $\{A_1, ..., A_n\}$:

| Approach | Method | Type |
|----------|--------|------|
| **Model-theoretic** | Show $B$ is a **semantic consequence** | Argue about all models |
| **Proof-theoretic** | Show $B$ is a **syntactic consequence** | Construct a formal proof |

**Key Relationship:**
- Soundness: Provable → Valid
- Completeness: Valid → Provable

4. (Undefinedness - unique feature!)

```

---

## 🔑 Key Concepts from Chapters 1-2

| Term | Definition | Page |
|------|------------|------|
| Simple Type Theory | | |
| Type | | |
| Base type | | |
| Function type | | |
| Type constructor | | |
| Alonzo | | |
| Higher-order logic | | |
| Typed lambda calculus | | |

---

## 📐 Important Notation

| Symbol | Meaning | Example |
|--------|---------|---------|
| α → β | | |
| λx.e | | |
| | | |
| | | |

---

## ✏️ Practice Exercises

**From Chapter 1-2:**

1. Exercise: 
   - My answer:
   - Correct?

2. Exercise:
   - My answer:
   - Correct?

3. Exercise:
   - My answer:
   - Correct?

---

## ❓ Questions

1. 
2. 
3. 

---

## 🔗 Resources

- STT Textbook Chapters 1-2
- Lecture slides (Avenue)
- [Original Church 1940 paper](https://www.jstor.org/stable/2266170) (optional)

---

## 💭 M&M Reflection

```
(Draft your M&M here)




```

---

## 📚 Reading Notes: Chapter 1

**Main Points:**
```




```

**Definitions to remember:**
```




```

**Questions from reading:**
```




```

---

## 📚 Reading Notes: Chapter 2

**Main Points:**
```




```

**Definitions to remember:**
```




```

**Questions from reading:**
```




```

---

*Completed: ⬜ Yes / ⬜ No*
