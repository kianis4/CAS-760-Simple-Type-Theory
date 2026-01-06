# 📖 Lecture 12: Software Support

> **Tools and systems for simple type theory**

---

## 📅 Lecture Info

| Item | Details |
|------|---------||
| **Week** | 12 |
| **Slides** | ✅ [12-software.pdf](./12-software.pdf) |
| **Textbook** | Chapter 16 |
| **Status** | ⬜ Not yet attended |

---

## ✅ Pre-Lecture Checklist

- [x] Slides downloaded ✅
- [ ] Skimmed slides before lecture
- [ ] Read Chapter 16 of STT textbook

## ✅ Post-Lecture Checklist

- [ ] Attended lecture
- [ ] Reviewed notes same day
- [ ] Explored at least one proof assistant
- [ ] Wrote M&M reflection

---

## 📋 Lecture Overview

**Source:** `12-software.pdf`  
**Total Slides:** 18  
**Textbook:** STT Chapter 16

### 📑 Lecture Outline (2 Sections)

| # | Section | Slides | Key Focus |
|---|---------|--------|----------|
| 1 | Software Support | 3-6 | Basic, advanced, fully integrated support |
| 2 | Final Remarks | 7-17 | Formal math, standard vs alternative approach, future work |

---

## 🎯 Learning Objectives

**Software Support:**
- [ ] Distinguish **basic**, **advanced**, and **fully integrated** software support
- [ ] Connect support categories to the tetrapod model aspects
- [ ] Describe what an Interactive Mathematical Laboratory (IML) would provide

**Formal Mathematics:**
- [ ] Define **formal mathematics** (logic + theories + development + morphisms)
- [ ] List the **five big benefits** of formal mathematics
- [ ] Compare **standard approach** (proof assistants, certification) vs **alternative approach** (communication, accessibility)
- [ ] Explain the "Formal Mathematics for the Masses" project goals

---

## 📝 Lecture Notes

---

### 1️⃣ Software Support (Slides 3-6)

**Basic Support** (Slide 4)
> The most basic support is software for processing Alonzo types and expressions.

| Approach | Description |
|----------|-------------|
| LaTeX commands | Represent Alonzo types/expressions in documents |
| Parser/printer | Read and display expressions |
| Type checker | Verify well-formedness |

**Advanced Support** (Slide 5)
> Corresponds to the **five aspects of the tetrapod model**:

| Aspect | Software Support |
|--------|------------------|
| **Concepts** | Definition editors, concept browsers |
| **Statements** | Theorem databases, statement validators |
| **Theories** | Theory editors, module systems |
| **Reasoning** | Proof assistants, automated provers |
| **Models** | Model checkers, interpreters |

**Fully Integrated Support** (Slide 6)
> An **Interactive Mathematical Laboratory (IML)** would fully integrate all support.

| Feature | Capability |
|---------|------------|
| Expression editor | Create and manipulate Alonzo expressions |
| Theory browser | Navigate theory graphs |
| Proof assistant | Interactive theorem proving |
| Model explorer | Construct and examine models |
| Library manager | Organize developments and morphisms |

> **Note:** An IML of this kind is needed for **large-scale mathematics formalization**.

---

### 2️⃣ Final Remarks (Slides 7-17)

**Course Objective Revisited** (Slide 8)
> Transform how logic is taught to students who will **actually use logic** in practice.

**What is Formal Mathematics?** (Slides 9-10)
> **Formal mathematics** is mathematics done with a formal logic:

| Step | Description |
|------|-------------|
| 1. Choose a formal logic | Language family with semantics and proof system |
| 2. Construct theories | Axiomatize mathematical structures |
| 3. Develop theories | Define concepts, state and prove theorems |
| 4. Connect theories | Build morphisms, transport results |

**Five Big Benefits of Formal Mathematics** (Slide 11)

| # | Benefit |
|---|--------|
| 1 | Mathematics done with **greater rigor** |
| 2 | **Conceptual errors** systematically discovered |
| 3 | Mathematics done with **software support** |
| 4 | Results can be **mechanically checked** |
| 5 | Mathematical knowledge can be **organized and reused** |

**Standard Approach** (Slide 12)
> Do mathematics with a **proof assistant**, all details formally proved and mechanically checked.

| Strength | Description |
|----------|-------------|
| Certification | Every theorem is machine-verified |
| Reliability | No hidden errors in proofs |
| Automation | Computer assists with proof search |

| Weakness | Description |
|----------|-------------|
| Effort | Very high formalization cost |
| Accessibility | Steep learning curve |
| Readability | Formal proofs often hard to understand |

**Campaign for Formal Mathematics** (Slide 13)
> For 60+ years, campaign to transform traditional practice using standard approach.

**Successes:**
- Four Color Theorem (Coq)
- Kepler Conjecture (HOL Light)
- Feit-Thompson Theorem (Coq)
- Liquid Tensor Experiment (Lean)

**Alternative Approach** (Slide 14)
> Focus on **communication** and **accessibility**:

| Principle | Description |
|-----------|-------------|
| Fully formal logic | But supports standard mathematical practice |
| Communication | Formal math should be readable |
| Accessibility | Tools usable by working mathematicians |
| Certification optional | Not everything needs machine verification |

**Formal Mathematics for the Masses** (Slide 15)
> A project to make formal mathematics:

| Goal | Description |
|------|-------------|
| More **useful** | Practical for everyday mathematics |
| More **accessible** | Lower barrier to entry |
| More **natural** | Looks like traditional mathematics |

**Results So Far** (Slide 16)

| Achievement | Description |
|-------------|-------------|
| **Alonzo** | Practice-oriented version of STT |
| **Proof system** | Formal proof system for Alonzo |
| **Module system** | For organizing theories and developments |
| **Textbook** | Graduate-level STT presentation |

**Future Work** (Slide 17)

| Project | Status |
|---------|--------|
| Paper on alternative approach | Planned |
| Expression editor for Alonzo | In development |
| Theory graph assistant | Planned |
| Full IML implementation | Long-term goal |

---

## 🔑 Key Concepts

| Term | Definition |
|------|------------|
| Basic support | Parser, printer, type checker for expressions |
| Advanced support | Tools for each tetrapod aspect |
| IML | Interactive Mathematical Laboratory |
| Formal mathematics | Math done with formal logic, theories, proofs |
| Standard approach | Proof assistant + mechanical certification |
| Alternative approach | Communication + accessibility focus |
| Proof assistant | Interactive theorem prover |
| Tetrapod model | 5 aspects: concepts, statements, theories, reasoning, models |

---

## 📚 Reading Notes: Chapter 16

**Key Takeaways:**
- Software support ranges from basic (LaTeX) to fully integrated (IML)
- Formal mathematics offers rigor, error detection, reuse
- Standard approach emphasizes certification; alternative emphasizes accessibility
- Alonzo is designed to support the alternative approach
- Future: better tools for working mathematicians

---

## 🖥️ Software Exploration

**System I explored:**

**How to install/access:**

**First impressions:**

**Potential for project:**

---

## 💭 M&M Reflection

```




```

---

*Completed: ⬜ Yes / ⬜ No*
