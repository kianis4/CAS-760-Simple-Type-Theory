# 📖 Lecture 4: Alonzo - Syntax and Semantics

> **The heart of the course - understanding Alonzo deeply**

---

## 📅 Lecture Info

| Item | Details |
|------|---------||
| **Week** | 4-6 |
| **Slides** | ✅ [4-alonzo.pdf](./4-alonzo.pdf) |
| **Textbook** | Chapters 4, 5, 6, 7 |
| **Status** | ⬜ Not yet attended |

---

## ✅ Pre-Lecture Checklist

- [x] Slides downloaded ✅
- [ ] Skimmed slides before lecture
- [ ] Read Chapters 4-7 of STT textbook

## ✅ Post-Lecture Checklist

- [ ] Attended all lectures on this topic
- [ ] Reviewed notes after each lecture
- [ ] Completed key concepts below
- [ ] Practice writing Alonzo expressions
- [ ] Wrote M&M reflections

---

## 📋 Lecture Overview

**Source:** `4-alonzo.pdf`  
**Total Slides:** 44  
**Textbook:** STT Chapters 4-7

### 📑 Lecture Outline (4 Sections)

| # | Section | Slides | Key Focus |
|---|---------|--------|----------|
| 1 | Syntax | 3-14 | Notation, symbols, types, expressions, languages |
| 2 | Semantics | 15-25 | Frames, interpretations, general/standard models |
| 3 | Additional Notation | 26-38 | Boolean ops, quantifiers, sets, tuples, quasitypes |
| 4 | Beta-Reduction & Substitution | 39-43 | β-reduction theorem, α-conversion |

---

## 🎯 Learning Objectives

**Knowledge:**
- [ ] Distinguish formal vs compact notation for Alonzo
- [ ] Define types inductively (base types, function types, product types)
- [ ] Define expressions inductively (variables, constants, application, abstraction, description)
- [ ] Explain bound/free variables and substitution in Alonzo
- [ ] Define languages as pairs $L = (B, C)$ of base types and constants
- [ ] Define frames, interpretations, and assignments
- [ ] Distinguish general models from standard models
- [ ] State satisfiability, validity, and semantic consequence
- [ ] Apply beta-reduction and alpha-conversion theorems

**Skills:**
- [ ] Write well-typed Alonzo expressions
- [ ] Determine if expressions are well-formed
- [ ] Use notational definitions (quantifiers, sets, tuples)

---

## 📝 Lecture Notes

---

### 1️⃣ Syntax (Slides 3-14)

**Two Kinds of Notation** (Slide 4)
| Type | Description | Use |
|------|-------------|-----|
| **Formal** | Fully explicit, unambiguous | Machine processing |
| **Compact** | Abbreviated, readable | Human communication |

**Symbols** (Slide 5)
| Symbol Set | Description |
|------------|-------------|
| $S_{bt}$ | Base type symbols: $A, B, C, ..., X, Y, Z$ |
| $S_{var}$ | Variable symbols |
| $S_{con}$ | Constant symbols |

**Metavariables** (Slide 6)
| Metavariable | Ranges Over |
|--------------|-------------|
| $a, b$, etc. | $S_{bt}$ (base types) |
| $f, g, h, ..., x, y, z$ | $S_{var}$ (variables) |
| $\alpha, \beta, \gamma$ | Types |
| $A, B, C$ | Expressions |

**Types** (Slides 7-8) - Defined inductively:

| Formation Rule | Notation | Meaning |
|----------------|----------|--------|
| Base type | $a$ | Base type symbol |
| Boolean | $o$ | Type of truth values $\mathbb{B} = \{t, f\}$ |
| Function | $\alpha \to \beta$ | Functions from $D_\alpha$ to $D_\beta$ |
| Product | $\alpha \times \beta$ | Pairs from $D_\alpha \times D_\beta$ |

**Expressions** (Slides 9-11) - Defined inductively:

| Formation Rule | Formal | Compact | Type |
|----------------|--------|---------|------|
| Variable | $Var(x, \alpha)$ | $(x : \alpha)$ | $\alpha$ |
| Constant | $Con(c, \alpha)$ | $(c : \alpha)$ | $\alpha$ |
| Application | $App(F, A)$ | $F_{\alpha \to \beta} A_\alpha$ | $\beta$ |
| Abstraction | $Abs(x, \alpha, B)$ | $\lambda x : \alpha . B_\beta$ | $\alpha \to \beta$ |
| Description | $Desc(x, \alpha, A)$ | $I x : \alpha . A_o$ | $\alpha$ |

**Bound and Free Variables** (Slide 12)
- Occurrence of $(x : \alpha)$ in $B$ is **bound** if within:
  - $\lambda x : \alpha . C$ or
  - $I x : \alpha . C$
- Otherwise it is **free**
- Substitution: $B[(x : \alpha) \mapsto A]$

**Languages** (Slides 13-14)
$$L = (B, C) \text{ where:}$$
- $B$ = finite set of base types
- $C$ = set of typed constants $(c : \alpha)$

**Language Extension:** $L_1 \subseteq L_2$ if $B_1 \subseteq B_2$ and $C_1 \subseteq C_2$

---

### 2️⃣ Semantics (Slides 15-25)

**Frames** (Slide 16)
$$\mathcal{D} = \{D_\alpha \mid \alpha \in \mathcal{T}(L)\}$$
- Collection of nonempty sets, one for each type
- $D_o = \mathbb{B} = \{t, f\}$ (boolean values)
- $D_{\alpha \to \beta} \subseteq$ set of functions from $D_\alpha$ to $D_\beta$

**Interpretations and Assignments** (Slide 17)
- **Interpretation:** $M = (\mathcal{D}, I)$ where $I$ assigns values to constants
- **Assignment:** $\phi : S_{var} \to \bigcup D_\alpha$ mapping variables to values

**General Models** (Slides 18-20)

**Valuation Function** $V^M_\phi$:
| Expression | Valuation |
|------------|----------|
| Variable $(x : \alpha)$ | $\phi(x)$ |
| Constant $(c : \alpha)$ | $I(c)$ |
| Application $F A$ | $V^M_\phi(F)(V^M_\phi(A))$ |
| Abstraction $\lambda x. B$ | Function mapping $a$ to $V^M_{\phi[x \mapsto a]}(B)$ |

**Key Results:**
- **Proposition:** General models for $L$ exist
- **Theorem:** Alonzo satisfies the three principles of TATU (Traditional Approach To Undefinedness)

**Finite and Standard Models** (Slide 21)
- $M$ is **finite** iff $D^M_\alpha$ is finite for all base types $\alpha$
- $M$ is **standard** iff $D_{\alpha \to \beta}$ contains ALL functions from $D_\alpha$ to $D_\beta$

**Satisfiability, Validity, Consequence** (Slides 22-23)

| Concept | Notation | Definition |
|---------|----------|------------|
| $\phi$ satisfies $A$ in $M$ | $M \models_\phi A_o$ | $V^M_\phi(A_o) = t$ |
| $A$ satisfiable in $M$ | | $M \models_\phi A$ for some $\phi$ |
| $A$ valid in $M$ | $M \models A$ | $M \models_\phi A$ for all $\phi$ |
| $A$ valid | $\models A$ | Valid in all general models |
| Semantic consequence | $\Gamma \models A$ | $A$ valid in all models of $\Gamma$ |

**Standard vs General Semantics** (Slide 25)
| Semantics | Based on | Use |
|-----------|----------|-----|
| **General** | General models | Logic-oriented, proof theory |
| **Standard** | Standard models | Mathematics-oriented, full function spaces |

---

### 3️⃣ Additional Notation (Slides 26-38)

**Boolean Operators** (Slide 27)
| Notation | Definition |
|----------|------------|
| $T_o$ | $(\lambda x : o . x) = (\lambda x : o . x)$ |
| $F_o$ | $(\lambda x : o . T_o) = (\lambda x : o . x)$ |
| $\neg A$ | $A = F$ |
| $A \land B$ | $(\lambda f. f\, T\, T) = (\lambda f. f\, A\, B)$ |

**Quantifiers** (Slide 29)
| Notation | Definition |
|----------|------------|
| $\forall x : \alpha . A_o$ | $(\lambda x : \alpha . T_o) = (\lambda x : \alpha . A_o)$ |
| $\exists x : \alpha . A_o$ | $\neg (\forall x : \alpha . \neg A_o)$ |
| $\exists! x : \alpha . A_o$ | Unique existence |

**Definedness** (Slide 30)
| Notation | Meaning |
|----------|--------|
| $A \downarrow$ | $A$ is defined |
| $A \uparrow$ | $A$ is undefined |
| $\bot_\alpha$ | Canonical undefined value of type $\alpha$ |

**Sets** (Slide 31)
| Notation | Definition |
|----------|------------|
| $\{\alpha\}$ | $\alpha \to o$ (type of sets of $\alpha$) |
| $A \in B_{\{\alpha\}}$ | $B_{\{\alpha\}}\, A$ |
| $\{x : \alpha \mid P\}$ | $\lambda x : \alpha . P$ |

**Tuples** (Slide 32)
| Notation | Meaning |
|----------|--------|
| $(\alpha_1, ..., \alpha_n)$ | Product type |
| $(A_1, ..., A_n)$ | Tuple expression |

**Functions** (Slide 33)
| Notation | Definition |
|----------|------------|
| $id_{\alpha \to \alpha}$ | $\lambda x : \alpha . x$ |
| $dom(f)$ | Domain of function $f$ |
| $f \circ g$ | Function composition |

**Quasitypes** (Slides 35-37)
- Allow restricting types to subsets
- $(\lambda x : Q_{\{\alpha\}} . B)$ - abstraction over quasitype
- $(\forall x : Q_{\{\alpha\}} . A_o)$ - quantification over quasitype

---

### 4️⃣ Beta-Reduction and Substitution (Slides 39-43)

**⭐ Beta-Reduction Theorem** (Slide 40)
> If $A$ is free for $(x : \alpha)$ in $B$, then:
> $$A \downarrow \Rightarrow (\lambda x : \alpha . B) A \simeq B[(x : \alpha) \mapsto A]$$

**⭐ Universal Instantiation Theorem** (Slide 41)
> If $A$ is free for $(x : \alpha)$ in $B_o$, then:
> $$(\forall x : \alpha . B_o) \land A \downarrow \Rightarrow B_o[(x : \alpha) \mapsto A]$$

**⚠️ Invalid Beta-Reduction Example** (Slide 42)
- Shows why definedness condition is necessary
- $F = \lambda x : \alpha . \lambda y : \beta . (x : \alpha)$
- $F\, A$ should be constant function if $A$ defined, undefined if $A$ undefined

**⭐ Alpha-Conversion Theorem** (Slide 43)
> If $(y : \alpha)$ is not free in $B$ and $(y : \alpha)$ is free for $(x : \alpha)$ in $B$, then:
> $$\lambda x : \alpha . B \simeq \lambda y : \alpha . B[(x : \alpha) \mapsto (y : \alpha)]$$

---

## 🔑 Key Concepts Summary

| Term | Definition |
|------|------------|
| Type | String classifying expressions by value |
| Expression | Well-formed typed term of Alonzo |
| Language | Pair $L = (B, C)$ of base types and constants |
| Frame | Collection of domains $\{D_\alpha\}$ for each type |
| Interpretation | Pair $M = (\mathcal{D}, I)$ with frame and constant meanings |
| General model | Interpretation where valuation is well-defined |
| Standard model | General model with full function spaces |
| Beta-reduction | $(\lambda x. B) A \simeq B[x \mapsto A]$ when $A$ defined |

```




```

### Truth and Validity

```




```

### Undefinedness in Semantics

```




```

---

## 📝 Chapter 7: Standard Semantics

### Standard Models

**Definition:**
```




```

**Difference from General:**
```




```

### Standard Validity

```




```

---

## 🔑 Key Concepts

### Chapter 4 (Syntax)

| Term | Definition | Example |
|------|------------|---------|
| Type | | |
| Expression | | |
| Well-formed | | |
| Definite description | | |
| Partial function | | |

### Chapters 5-7 (Semantics)

| Term | Definition | Example |
|------|------------|---------|
| Frame | | |
| Interpretation | | |
| Denotation | | |
| Validity | | |
| General model | | |
| Standard model | | |

---

## 📐 Important Notation

| Symbol | Meaning | Used for |
|--------|---------|----------|
| | | |
| | | |
| | | |
| | | |

---

## ✏️ Practice: Writing Alonzo Expressions

**Exercise 1:** Write a type for...
```

```

**Exercise 2:** Write an expression for...
```

```

**Exercise 3:** Is this expression defined?
```

```

---

## 📚 Reading Notes

### Chapter 4 Notes
```




```

### Chapter 5 Notes
```




```

### Chapter 6 Notes
```




```

### Chapter 7 Notes
```




```

---

## ❓ Questions

1. 
2. 
3. 

---

## 💭 M&M Reflections

**Week 4:**
```


```

**Week 5:**
```


```

**Week 6:**
```


```

---

*Completed: ⬜ Yes / ⬜ No*
