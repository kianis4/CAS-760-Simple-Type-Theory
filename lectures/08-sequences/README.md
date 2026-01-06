# 📖 Lecture 8: Sequences

> **Working with sequences in Alonzo**

---

## 📅 Lecture Info

| Item | Details |
|------|---------||
| **Week** | 9 |
| **Slides** | ✅ [8-sequences.pdf](./8-sequences.pdf) |
| **Textbook** | Chapter 11 |
| **Status** | ⬜ Not yet attended |

---

## ✅ Pre-Lecture Checklist

- [x] Slides downloaded ✅
- [ ] Skimmed slides before lecture
- [ ] Read Chapter 11 of STT textbook

## ✅ Post-Lecture Checklist

- [ ] Attended lecture
- [ ] Reviewed notes same day
- [ ] Practice exercises
- [ ] Wrote M&M reflection

---

## 📋 Lecture Overview

**Source:** `8-sequences.pdf`  
**Total Slides:** 14  
**Textbook:** STT Chapter 11

### 📑 Lecture Outline (3 Sections)

| # | Section | Slides | Key Focus |
|---|---------|--------|----------|
| 1 | Background | 3-6 | Domain constructions, undefinedness benefits, basic definitions |
| 2 | Systems of Natural Numbers | 7-9 | $E_{nat}$ components, arithmetic operations |
| 3 | Notational Definitions for Sequences | 10-13 | Streams, lists, nil, cons, sequence facts |

---

## 🎯 Learning Objectives

- [ ] Represent domain constructions in Alonzo (function space, power set, product, disjoint union)
- [ ] Explain benefits of undefined expressions for sequences
- [ ] Represent infinite sequences as total functions $s : \mathbb{N} \to A$
- [ ] Represent finite sequences as partial functions $s : \mathbb{N} \rightharpoonup A$
- [ ] Define systems of natural numbers $E_{nat}$
- [ ] Use notational definitions: $sequences\{\alpha\}$, $nil$, $cons$, $[\,]$
- [ ] State and apply sequence facts/propositions

---

## 📝 Lecture Notes

---

### 1️⃣ Background (Slides 3-6)

**Domain Constructions in Alonzo** (Slide 4)

| Construction | Alonzo Representation | Description |
|--------------|----------------------|-------------|
| Function space | $\alpha \to \beta$ | Functions from $\alpha$ to $\beta$ |
| Power set | $\{\alpha\} = \alpha \to o$ | Sets as characteristic functions |
| Product | $\alpha \times \beta$ | Ordered pairs |
| Disjoint union | $\alpha + \beta$ | Tagged union |

**Benefits of Undefined Expressions** (Slide 5)

The traditional approach to undefinedness facilitates formalization of:

| Value Type | Representation | Key Feature |
|------------|----------------|-------------|
| Partial functions | $f : \alpha \to \beta$ | $f(x)$ undefined for some $x$ |
| Finite sequences | $s : \mathbb{N} \rightharpoonup A$ | Undefined beyond length |
| Partial operations | e.g., $1/x$ | Undefined at $x = 0$ |

**Basic Definitions** (Slide 6)

| Sequence Type | Representation | Description |
|---------------|----------------|-------------|
| **Infinite sequence** | $s : \mathbb{N} \to A$ | Total function, defined for all $n$ |
| **Finite sequence** | $s : \mathbb{N} \rightharpoonup A$ | Partial function, defined for $0, ..., k-1$ |
| **Stream** | $s : \mathbb{N} \to A$ | Infinite sequence (synonym) |
| **List** | $s : \mathbb{N} \rightharpoonup A$ | Finite sequence (synonym) |

---

### 2️⃣ Systems of Natural Numbers (Slides 7-9)

**Definition** (Slide 8)
> Let $T = (L, \Gamma)$ be a theory. A **system of natural numbers** is a set:
> $$E_{nat} = \{C_\mathbb{N}, 0, S, P, +, \cdot, \leq\}$$

**Components** (Slide 9)

| Symbol | Type | Description |
|--------|------|-------------|
| $C_\mathbb{N}$ | $\{N\}$ | The set/type of natural numbers |
| $0$ | $N$ | Zero constant |
| $S$ | $N \to N$ | Successor function |
| $P$ | $N \to N$ | Predecessor function |
| $+$ | $N \to N \to N$ | Addition |
| $\cdot$ | $N \to N \to N$ | Multiplication |
| $\leq$ | $N \to N \to o$ | Less-than-or-equal predicate |

**Theory $T_{nat}$:**
- Extends PA with predecessor, addition, multiplication, ordering
- Provides foundation for sequence operations

---

### 3️⃣ Notational Definitions for Sequences (Slides 10-13)

**Sequence Type Notation** (Slide 11)

| Notation | Definition | Description |
|----------|------------|-------------|
| $sequences\{\alpha\}$ | $C_\mathbb{N} \to \{\alpha\}$ | Type of sequences of $\alpha$ |
| $streams\{\alpha\}$ | Total functions in $sequences\{\alpha\}$ | Infinite sequences |
| $lists\{\alpha\}$ | Partial functions in $sequences\{\alpha\}$ | Finite sequences |

**List Constructors** (Slide 12)

| Notation | Definition | Description |
|----------|------------|-------------|
| $nil_\alpha$ | $\lambda n : N . \bot_\alpha$ | Empty list (always undefined) |
| $[\,]_\alpha$ | $nil_\alpha$ | Alternative empty list notation |
| $cons$ | $\lambda x. \lambda s. \lambda n. ...$ | Prepend element to list |
| $[a, b, c]$ | $cons(a, cons(b, cons(c, nil)))$ | List literal notation |

**List Operations:**

| Operation | Type | Description |
|-----------|------|-------------|
| $head(s)$ | $\alpha$ | First element (undefined if empty) |
| $tail(s)$ | $sequences\{\alpha\}$ | All but first element |
| $length(s)$ | $N$ | Number of defined elements |
| $s(n)$ | $\alpha$ | n-th element (0-indexed) |

**Facts about Sequences** (Slide 13)

> **Proposition:** The following are valid in $T_{nat}$ for every type $\alpha$:

| Fact | Statement |
|------|----------|
| Empty list | $\forall n : N. nil(n) \uparrow$ |
| Cons head | $head(cons(x, s)) = x$ |
| Cons tail | $tail(cons(x, s)) = s$ |
| Length nil | $length(nil) = 0$ |
| Length cons | $length(cons(x, s)) = S(length(s))$ |

---

## 🔑 Key Concepts

| Term | Definition |
|------|------------|
| Infinite sequence | Total function $s : \mathbb{N} \to A$ |
| Finite sequence | Partial function $s : \mathbb{N} \rightharpoonup A$ |
| Stream | Synonym for infinite sequence |
| List | Synonym for finite sequence |
| $nil$ | Empty list (always undefined) |
| $cons(x, s)$ | Prepend $x$ to sequence $s$ |
| $E_{nat}$ | System of natural numbers |

---

## 📚 Reading Notes: Chapter 11

**Key Takeaways:**
- Sequences are functions from $\mathbb{N}$
- Finite sequences use undefinedness beyond their length
- List notation $[a, b, c]$ is sugar for nested $cons$
- Natural number system provides arithmetic for indexing

---

## 💭 M&M Reflection

```




```

---

*Completed: ⬜ Yes / ⬜ No*
