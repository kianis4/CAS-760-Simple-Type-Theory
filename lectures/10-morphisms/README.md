# 📖 Lecture 10: Morphisms

> **Connecting theories together**

---

## 📅 Lecture Info

| Item | Details |
|------|---------||
| **Week** | 11 |
| **Slides** | ✅ [10-morphisms.pdf](./10-morphisms.pdf) |
| **Textbook** | Chapter 14 |
| **Status** | ⬜ Not yet attended |

---

## ✅ Pre-Lecture Checklist

- [x] Slides downloaded ✅
- [ ] Skimmed slides before lecture
- [ ] Read Chapter 14 of STT textbook
- [ ] Read Monoid Theory paper (Avenue)

## ✅ Post-Lecture Checklist

- [ ] Attended lecture
- [ ] Reviewed notes same day
- [ ] Practice exercises
- [ ] Wrote M&M reflection

---

## 📋 Lecture Overview

**Source:** `10-morphisms.pdf`  
**Total Slides:** 62  
**Textbook:** STT Chapter 14

### 📑 Lecture Outline (5 Sections)

| # | Section | Slides | Key Focus |
|---|---------|--------|----------|
| 1 | Little Theories Method | 3-6 | Big vs little theories, abstraction, reuse |
| 2 | Theory Morphisms | 7-33 | Translations, morphisms, obligations, interfaces |
| 3 | Development Morphisms | 34-49 | Dev translations, transportations, modules |
| 4 | Mathematics Libraries | 50-55 | Theory graphs, development graphs, realm graphs |
| 5 | Theory Graph Combinators | 56-61 | Extension, renaming, combination, instantiation |

---

## 🎯 Learning Objectives

**Knowledge:**
- [ ] Explain what a **morphism** is and what it preserves
- [ ] Compare **big theory** vs **little theories** method
- [ ] Define **theory translation** $\Phi = (\phi, \psi)$ from $T_1$ to $T_2$
- [ ] Define when a translation is a **morphism** (axiom preservation)
- [ ] State the **obligations** of a translation
- [ ] Define **faithful morphism** and **interface**
- [ ] Define **development morphism** and **transportations**
- [ ] Explain **theory graphs**, **development graphs**, **realm graphs**

**Skills:**
- [ ] Use morphisms to transport statements between theories/developments
- [ ] Write theory translation definition/extension modules
- [ ] Write definition and theorem transportation modules
- [ ] Apply theory graph combinators (extension, renaming, combination, instantiation)

---

## 📝 Lecture Notes

---

### 1️⃣ Little Theories Method (Slides 3-6)

**Motivating Example** (Slide 4)
> The structure $(\mathbb{R}, 0, 1, +, \cdot, -, ^{-1})$ contains **two monoids**:
> - $(\mathbb{R}, 0, +)$ — additive monoid
> - $(\mathbb{R}, 1, \cdot)$ — multiplicative monoid

**Two Approaches to Formalizing Math** (Slide 5)

| Approach | Description | Example |
|----------|-------------|---------|
| **Big theory method** | One massive theory with everything | ZFC set theory |
| **Little theories method** | Many small, interconnected theories | Network of theories |

**Advantages of Little Theories** (Slide 6)
1. **Abstraction:** Each topic developed at appropriate level
2. **Reuse:** Theorems proved once, applied everywhere
3. **Modularity:** Theories can be combined flexibly
4. **Clarity:** Assumptions made explicit

---

### 2️⃣ Theory Morphisms (Slides 7-33)

**Theory Translations** (Slides 9-12)
> Let $T_i = (L_i, \Gamma_i)$ where $L_i = (B_i, C_i)$ for $i \in \{1, 2\}$.
>
> A **(theory) translation** from $T_1$ to $T_2$ is a pair $\Phi = (\phi, \psi)$ where:

| Component | Type | Description |
|-----------|------|-------------|
| $\phi$ | $B_1 \to T_2[Q_2]$ | Maps base types to type expressions |
| $\psi$ | $C_1 \to E_2$ | Maps constants to expressions |

**Translation Properties** (Slide 12)
| Property | Condition |
|----------|----------|
| **Identity** | $\phi$ and $\psi$ are identity mappings |
| **Inclusion** | $T_1 \subseteq T_2$ and identity translation |
| **Renaming** | Bijective mappings (just name changes) |

**Theory Translation Module** (Slide 13)
```
Theory Translation Definition X.Y
  Name: NAME
  Source: T₁
  Target: T₂
  Type mapping: φ
  Constant mapping: ψ
```

#### Example Translations (Slides 14-24)

| Name | Source → Target | Key Mapping |
|------|-----------------|-------------|
| MON-to-GRP | MON → GRP | Identity (groups extend monoids) |
| PA-with-1-to-PA | PA-with-1 → PA | $1 \mapsto S(0)$ |
| DWTOWE-to-COF | Dense orders → COF | Order embeds in reals |
| RA-to-PA | Robinson → Peano | Inclusion |
| MON-to-COF-+ | MON → COF | $e \mapsto 0$, $* \mapsto +$ |
| MON-to-COF-· | MON → COF | $e \mapsto 1$, $* \mapsto \cdot$ |
| GRP-to-dual-GRP | GRP → GRP | $x * y \mapsto y * x$ |

**Theory Morphisms** (Slides 25-26)
> $\Phi$ is a **(theory) morphism** from $T_1$ to $T_2$ if:
> $$T_1 \vdash A_o \Rightarrow T_2 \vdash \Phi(A_o)$$
> for all sentences $A_o$ of $L_1$.

**Corollary:** If $T_1 \subseteq T_2$, the identity translation is an **inclusion morphism**.

**Obligations** (Slide 27)
> The **obligations** of a translation $\Phi$ are sentences of $L_2$ that must be proved:

| Obligation Type | Description |
|----------------|-------------|
| Type well-formedness | $\phi(a)$ is a valid type expression |
| Constant typing | $\psi(c)$ has correct type |
| Axiom preservation | Each axiom of $T_1$ translates to theorem of $T_2$ |

**Morphism Theorem** (Slide 28)
> **Lemma:** Let $\Phi = (\phi, \psi)$ be a translation from $T_1$ to $T_2$.
> If all obligations are satisfied, then $\Phi$ is a morphism.

**Faithful Morphisms & Interfaces** (Slides 31-32)
> A morphism $\Phi$ from $T_1$ to $T_2$ is **faithful** if:
> $$T_2 \vdash \Phi(A_o) \Rightarrow T_1 \vdash A_o$$

> An **interface** for theory $T$ is a faithful embedding from some $T_0$ to $T$.

**Theory Graph Example** (Slide 33)
```
        COF
       / | \
      /  |  \
   MON  GRP  DWTOWE
         |     \
    FUN-COMP    ...
```

---

### 3️⃣ Development Morphisms (Slides 34-49)

**Development Translations** (Slides 36-37)
> Let $D_i = (T_i, \sigma_i)$ be developments where $T'_i$ is the top theory.
>
> A **(development) translation** from $D_1$ to $D_2$ is $\Phi = (\phi, \psi)$ such that:
> - $\Phi$ is a theory translation from $T'_1$ to $T'_2$

**Development Translation Module** (Slide 38)
```
Development Translation Definition X.Y
  Name: NAME
  Source: D₁
  Target: D₂
  Type mapping: φ
  Constant mapping: ψ
```

**Example: PA to COF** (Slide 41)
```
Development Translation Definition (PA to COF)
  Name: PA-to-COF
  Source: Development of PA
  Target: Development of COF
  N ↦ {x : R | x ≥ 0 ∧ ∃n:N. x = n·1}
  0 ↦ 0
  S ↦ λx. x + 1
```

**Definition Transportation** (Slides 42-46)
> If $c = A$ is a definition in $D_1$ and $\Phi$ is a morphism to $D_2$:
> - Transport $c$ to $D_2$ as $\Phi(c) = \Phi(A)$

**Definition Transportation Module** (Slide 45)
```
Definition Transportation X.Y
  Name: NAME
  Via morphism: Φ
  Definition: c = A
  Result: Φ(c) = Φ(A)
```

**Theorem Transportation** (Slides 44, 47-48)
> If $B_o$ is a theorem of $D_1$ and $\Phi$ is a morphism to $D_2$:
> - $\Phi(B_o)$ is a theorem of $D_2$

**Theorem Transportation Module** (Slide 47)
```
Theorem Transportation X.Y
  Name: NAME
  Via morphism: Φ
  Theorem: B₀
  Result: Φ(B₀)
```

---

### 4️⃣ Mathematics Libraries (Slides 50-55)

**Theory Graphs** (Slide 51)
> A **theory graph** of Alonzo is a directed graph $G = (N, V)$ where:
> - $N$ = set of theories (nodes)
> - $V$ = set of morphisms (edges)

**Development Graphs** (Slides 52-53)
> A **development graph** supports four ways of developing:

| Method | Description |
|--------|-------------|
| Theory definition | Create new base theory |
| Theory extension | Add types/constants/axioms |
| Development | Add definitions and theorems |
| Transportation | Import via morphisms |

**Realm Graphs** (Slides 54-55)
> A **realm** consolidates knowledge about a mathematical theory.
>
> A **realm graph** is a directed graph $G = (N, V)$ where:
> - Nodes are realms (theory + its developments)
> - Edges are morphisms between realms

---

### 5️⃣ Theory Graph Combinators (Slides 56-61)

**Definition** (Slide 57)
> A **theory graph combinator** takes a theory graph $G$ plus arguments and produces a new graph $G'$.

| Combinator | Effect | Diagram |
|------------|--------|---------|
| **Extension** | Add to theory | $T \to T'$ |
| **Renaming** | Rename symbols | $T \to T'$ (isomorphic) |
| **Combination** | Merge theories | $T_1, T_2 \to T_1 + T_2$ |
| **Instantiation** | Specialize theory | $T_1 \to T_2$ via morphism |

**Theory Extension** (Slide 58)
- Adds new types, constants, or axioms: $T \to T'$

**Theory Renaming** (Slide 59)
- Bijective symbol renaming: $T \to T'$ (isomorphic)

**Theory Combination** (Slide 60)
```
    T₀
   / \
  T₁  T₂
   \ /
  T₁+T₂
```
- Pushout construction: combines shared base with distinct extensions

**Theory Instantiation** (Slide 61)
- Specialize abstract theory via morphism: $T_1 \to T_0 \to T_2$

---

## 🔑 Key Concepts

| Term | Definition |
|------|------------|
| Little theories method | Network of small, interconnected theories |
| Theory translation | Pair $(\phi, \psi)$ mapping types and constants |
| Theory morphism | Translation preserving theorems |
| Obligations | Proof requirements for morphism validity |
| Faithful morphism | Morphism that also reflects theorems |
| Interface | Faithful embedding into a theory |
| Development morphism | Morphism between developments |
| Transportation | Importing definitions/theorems via morphism |
| Theory graph | Network of theories and morphisms |
| Realm | Theory with all its developments |
| Combinator | Operation building new graphs from old |

---

## 📚 Reading Notes

### Chapter 14
- Morphisms are the key to reusing mathematical knowledge
- Little theories method enables modular mathematics
- Transportation moves results between theories automatically

### Monoid Theory Paper
- Practical example of the little theories method
- Shows how one theory (MON) serves many purposes

---

## 💭 M&M Reflection

```




```

---

*Completed: ⬜ Yes / ⬜ No*
