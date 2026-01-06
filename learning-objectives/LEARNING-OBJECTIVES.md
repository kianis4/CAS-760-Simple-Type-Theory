# 🎯 CAS 760 Learning Objectives

> **What you need to know and be able to do by the end of this course**

---

## 📋 Quick Navigation

- [Precondition (Prerequisites)](#-precondition-what-you-should-already-know)
- [Postcondition - Knowledge](#-postcondition-part-1-what-you-should-know)
- [Postcondition - Skills](#-postcondition-part-2-what-you-should-be-able-to-do)
- [Mapping to Syllabus](#-mapping-learning-objectives-to-syllabus)

---

## 📥 Precondition: What You Should Already Know

> **Self-Assessment:** Rate your confidence 1-5 (1=not confident, 5=very confident)

| Prerequisite | Confidence | Need Review? | Resources |
|--------------|------------|--------------|-----------|
| University-level mathematics | /5 | ⬜ | |
| Set theory (basic operations) | /5 | ⬜ | |
| Ordinals | /5 | ⬜ | |
| Cardinality | /5 | ⬜ | |
| First-order logic syntax | /5 | ⬜ | |
| First-order logic semantics | /5 | ⬜ | |
| First-order logic proofs | /5 | ⬜ | |
| Recursive definitions | /5 | ⬜ | |
| Proof by induction | /5 | ⬜ | |
| Mathematical proof techniques | /5 | ⬜ | |
| Decidability concepts | /5 | ⬜ | |

### 🚨 Action Items for Prerequisites

If any confidence < 3, schedule time to review BEFORE Week 2:

1. **First-Order Logic Review**: Covered in Lecture 1
2. **Set Theory**: Review ordinals and cardinality
3. **Induction**: Practice structural induction proofs

---

## 📤 Postcondition Part 1: What You Should KNOW

### 1a. Logical Principles of Predicate Logics

**Objective:** Understand the logical principles underlying predicate logics such as first-order logic and simple type theory.

| Sub-topic | Covered In | Understood? | Notes |
|-----------|------------|-------------|-------|
| What is a predicate logic | Lecture 1 | ⬜ | |
| Syntax vs semantics distinction | Lecture 1, 4 | ⬜ | |
| Types and type systems | Lecture 2 | ⬜ | |
| Why simple type theory extends FOL | Lecture 2 | ⬜ | |
| Church's type theory foundations | Lecture 2 | ⬜ | |

**Key Questions to Answer:**
- [ ] What makes a logic "predicate"?
- [ ] How does STT differ from first-order logic?
- [ ] Why was Church's type theory created?

---

### 1b. General and Standard Semantics for Simple Type Theory

**Objective:** Understand the general and standard semantics for simple type theory.

| Sub-topic | Covered In | Understood? | Notes |
|-----------|------------|-------------|-------|
| General semantics definition | Ch 5-6, Lecture 4 | ⬜ | |
| Standard semantics definition | Ch 5-6, Lecture 4 | ⬜ | |
| Interpretation of types | Ch 5, Lecture 4 | ⬜ | |
| Interpretation of expressions | Ch 6, Lecture 4 | ⬜ | |
| Validity and satisfaction | Ch 7, Lecture 4 | ⬜ | |

**Key Questions to Answer:**
- [ ] What is a frame in STT?
- [ ] What is an interpretation?
- [ ] How do general and standard semantics differ?
- [ ] What does it mean for an expression to be valid?

---

### 1c. Mathematical Structures in Alonzo

**Objective:** Know what mathematical structures are and how they can be specified in a simple type theory like Alonzo.

| Sub-topic | Covered In | Understood? | Notes |
|-----------|------------|-------------|-------|
| What is a mathematical structure | Ch 9, Lecture 6 | ⬜ | |
| Theories in Alonzo | Ch 9, Lecture 6 | ⬜ | |
| Specifying a single structure | Ch 9, Lecture 6 | ⬜ | |
| Specifying a class of structures | Ch 9, Lecture 6 | ⬜ | |
| Examples: groups, monoids, etc. | Monoid paper | ⬜ | |

**Key Questions to Answer:**
- [ ] What components define a mathematical structure?
- [ ] How does a theory specify a structure?
- [ ] What's the difference between specifying one structure vs many?

---

### 1d. Reasoning with Undefinedness

**Objective:** Understand how to reason with undefinedness in a logic like Alonzo that admits undefined expressions.

| Sub-topic | Covered In | Understood? | Notes |
|-----------|------------|-------------|-------|
| What are undefined expressions | Ch 4, Lecture 4 | ⬜ | |
| Partial functions | Ch 4, Lecture 4 | ⬜ | |
| Definite descriptions | Ch 4, Lecture 4 | ⬜ | |
| Three-valued logic aspects | Ch 7, Lecture 4 | ⬜ | |
| Definedness conditions | Ch 8, Lecture 5 | ⬜ | |

**Key Questions to Answer:**
- [ ] Why allow undefined expressions?
- [ ] How does undefinedness affect truth values?
- [ ] What proof rules handle undefinedness?

---

### 1e. Proof Systems for Simple Type Theory

**Objective:** Understand proof systems for simple type theory.

| Sub-topic | Covered In | Understood? | Notes |
|-----------|------------|-------------|-------|
| Natural deduction | Ch 8, Lecture 5 | ⬜ | |
| Proof rules for Alonzo | Ch 8, Lecture 5 | ⬜ | |
| Soundness | Ch 8, Lecture 5 | ⬜ | |
| Completeness | Ch 8, Lecture 5 | ⬜ | |
| Proof strategies | App A-C, Lecture 5 | ⬜ | |

**Key Questions to Answer:**
- [ ] What proof rules are used in Alonzo?
- [ ] Is the proof system sound? Complete?
- [ ] How do you construct a proof in Alonzo?

---

### 1f. The Little Theories Method

**Objective:** Understand the little theories method for organizing mathematical knowledge.

| Sub-topic | Covered In | Understood? | Notes |
|-----------|------------|-------------|-------|
| What is the little theories method | Ch 12-14, Lecture 9-10 | ⬜ | |
| Theory networks | Ch 14, Lecture 10 | ⬜ | |
| Theory morphisms | Ch 14, Lecture 10 | ⬜ | |
| Advantages of little theories | Ch 14, Lecture 10 | ⬜ | |
| Monoid example | Monoid paper | ⬜ | |

**Key Questions to Answer:**
- [ ] What problem does the little theories method solve?
- [ ] What is a theory morphism?
- [ ] How do you organize a mathematics library?

---

### 1g. Software Systems for Simple Type Theory

**Objective:** Know what kinds of software systems support the use of simple type theory.

| Sub-topic | Covered In | Understood? | Notes |
|-----------|------------|-------------|-------|
| Proof assistants | Ch 16, Lecture 12 | ⬜ | |
| IMPS system | Ch 16, Lecture 12 | ⬜ | |
| Isabelle/HOL | Ch 16, Lecture 12 | ⬜ | |
| Other STT-based systems | Ch 16, Lecture 12 | ⬜ | |
| Software project system | Project | ⬜ | |

**Key Questions to Answer:**
- [ ] What software systems use simple type theory?
- [ ] How do proof assistants work?
- [ ] What can you do with these systems?

---

## 📤 Postcondition Part 2: What You Should BE ABLE TO DO

### 2a. Express and Reason About Mathematical Ideas in STT

**Objective:** Express and reason about mathematical ideas in simple type theory.

| Skill | Practice Opportunities | Mastered? |
|-------|----------------------|-----------|
| Write types in Alonzo | Assignments 1-4 | ⬜ |
| Write expressions in Alonzo | Assignments 1-4 | ⬜ |
| Write formulas in Alonzo | Assignments 1-4 | ⬜ |
| Prove theorems in Alonzo | Assignments 1-4 | ⬜ |
| Translate math to Alonzo | Assignments 1-4 | ⬜ |

**Practice Checklist:**
- [ ] Wrote at least 10 types
- [ ] Wrote at least 20 expressions
- [ ] Proved at least 5 theorems
- [ ] Translated 3+ mathematical concepts

---

### 2b. Write Theories for Mathematical Structures

**Objective:** Write a theory in simple type theory to specify a single mathematical structure or a collection of similar mathematical structures.

| Skill | Practice Opportunities | Mastered? |
|-------|----------------------|-----------|
| Define a theory | Assignments, Dev Project | ⬜ |
| Specify axioms | Assignments, Dev Project | ⬜ |
| Specify a single structure | Dev Project Part 1 | ⬜ |
| Specify a class of structures | Dev Project Part 1 | ⬜ |

**Practice Checklist:**
- [ ] Wrote theory for a simple structure (e.g., monoid)
- [ ] Wrote theory with axioms
- [ ] Completed Development Project Part 1

---

### 2c. Build Mathematics Libraries with Theory Morphisms

**Objective:** Build a mathematics library as a network of theories connected by theory morphisms.

| Skill | Practice Opportunities | Mastered? |
|-------|----------------------|-----------|
| Create theory developments | Dev Project Part 2 | ⬜ |
| Define theory morphisms | Dev Project Part 2 | ⬜ |
| Connect theories in a graph | Dev Project Part 2 | ⬜ |
| Organize mathematical knowledge | Dev Project Part 2 | ⬜ |

**Practice Checklist:**
- [ ] Created at least 3 connected theories
- [ ] Defined at least 2 morphisms
- [ ] Completed Development Project Part 2

---

## 🗺️ Mapping Learning Objectives to Syllabus

| Syllabus Topic | Learning Objectives Covered |
|----------------|----------------------------|
| 0. Course Overview | Overview of all objectives |
| 1. Review of First-Order Logic | Prerequisite, 1a |
| 2. Intro to Simple Type Theory | 1a, 1b |
| 3. Preliminary Concepts | 1a, 1b |
| 4. Alonzo: Syntax & Semantics | 1b, 1c, 1d, 2a |
| 5. Proof Systems | 1e, 2a |
| 6. Theories | 1c, 2a, 2b |
| 7. Inductive Sets and Types | 1c, 2a |
| 8. Sequences | 1c, 2a |
| 9. Developments | 1f, 2b, 2c |
| 10. Morphisms | 1f, 2c |
| 11. Alonzo Variants | 1a, 1b |
| 12. Software Support | 1g |
| 13. Project Presentations | All skills (2a, 2b, 2c) |

---

## ✅ Final Self-Assessment

### Knowledge Objectives (Complete before end of course)

| Objective | Confident? | Evidence |
|-----------|------------|----------|
| 1a. Logical principles | ⬜ | |
| 1b. Semantics | ⬜ | |
| 1c. Mathematical structures | ⬜ | |
| 1d. Undefinedness | ⬜ | |
| 1e. Proof systems | ⬜ | |
| 1f. Little theories method | ⬜ | |
| 1g. Software systems | ⬜ | |

### Skill Objectives (Complete before end of course)

| Objective | Confident? | Evidence |
|-----------|------------|----------|
| 2a. Express & reason in STT | ⬜ | Assignments |
| 2b. Write theories | ⬜ | Dev Project |
| 2c. Build libraries | ⬜ | Dev Project |

---

*Track your progress here throughout the semester!*
