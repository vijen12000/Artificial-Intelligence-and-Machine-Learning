## Part 1 – Propositional Logic

---

# Learning Objectives

After this chapter you should be able to:

* Explain Logical Agents
* Define Knowledge Base
* Explain Knowledge Representation
* Understand Propositional Logic
* Explain Logical Connectives
* Evaluate Truth Tables
* Explain Models
* Explain Entailment
* Understand Inference

---

# 1. Why Logic?

Search algorithms solve

Problems

↓

Logic allows

Reasoning.

Instead of

Searching blindly,

AI can

Infer

New facts.

---

Example

```
All humans are mortal.

Socrates is human.

↓

Socrates is mortal.
```

---

# 2. Logical Agent ⭐⭐⭐⭐⭐

A Logical Agent

Stores knowledge

and

Uses logic

to make decisions.

It consists of:

```
Environment
      ↓
Percepts
      ↓
Knowledge Base
      ↓
Inference Engine
      ↓
Action
```

---

# 3. Knowledge Base (KB) ⭐⭐⭐⭐⭐

A Knowledge Base is

A collection

of

Facts

and

Rules.

Example

```
Rain

Clouds

Wet Road
```

---

Example Rule

```
IF Rain

↓

Road Wet
```

---

# 4. Components of Knowledge-Based System ⭐⭐⭐⭐⭐

Your PT question asked this directly.

Correct components are:

✅ Knowledge Base

✅ Inference Engine

Not

❌ Utility Function

❌ Transition Model

---

# Architecture

```
Knowledge Base

↓

Inference Engine

↓

New Knowledge
```

---

# 5. Knowledge Representation

Knowledge must be stored

in a structured way.

Types

* Facts
* Rules
* Relationships

---

Example

```
Bird(Tweety)

Bird(x)

↓

CanFly(x)
```

---

# 6. Sentences

A sentence

is

A logical statement.

Example

```
Sky is blue.
```

---

# 7. Propositional Logic ⭐⭐⭐⭐⭐

Simplest form

of logic.

A proposition

is either

True

or

False.

Nothing in between.

---

Examples

```
P

Q

R
```

---

Example

```
P

=

"It is raining."
```

---

# 8. Logical Connectives ⭐⭐⭐⭐⭐

These appeared directly in your PT.

---

## NOT (¬)

Negation

```
P

↓

NOT P
```

Example

```
Rain

↓

Not Rain
```

---

Truth Table

| P | ¬P |
| - | -- |
| T | F  |
| F | T  |

---

## AND (∧)

Conjunction

Both

must be true.

Example

```
Rain

AND

Wind
```

Truth Table

| P | Q | P∧Q |
| - | - | --- |
| T | T | T   |
| T | F | F   |
| F | T | F   |
| F | F | F   |

PT Question

Correct Answer

✔ Both parts

must be true.

---

## OR (∨)

Disjunction

At least

one

must be true.

Truth Table

| P | Q | P∨Q |
| - | - | --- |
| T | T | T   |
| T | F | T   |
| F | T | T   |
| F | F | F   |

PT Question

✔ Requires at least one true.

---

## Implication (→)

"If"

```
P

↓

Q
```

Means

If P

Then Q.

Truth Table

| P | Q | P→Q |
| - | - | --- |
| T | T | T   |
| T | F | F   |
| F | T | T   |
| F | F | T   |

Notice

False premise

↓

Always True.

This often surprises students and is a favorite MCQ.

---

## Biconditional (↔)

Means

Both

have same value.

```
P

IFF

Q
```

Truth Table

| P | Q | P↔Q |
| - | - | --- |
| T | T | T   |
| T | F | F   |
| F | T | F   |
| F | F | T   |

---

# 9. Truth Table ⭐⭐⭐⭐⭐

Truth tables determine

whether a formula

is

True

or

False.

Example

```
P ∧ Q
```

Evaluate

All combinations

of P

and Q.

---

# 10. Model ⭐⭐⭐⭐⭐

A

Model

assigns

True/False

values

to every symbol.

This appeared directly

in your PT.

Example

```
P=True

Q=False
```

This assignment

is

a Model.

---

# 11. Entailment ⭐⭐⭐⭐⭐

Notation

```
KB ⊨ α
```

Meaning

Knowledge Base

logically implies

α.

If KB

is true,

then

α

must also be true.

---

Example

```
All humans are mortal.

Socrates is human.

↓

Socrates is mortal.
```

---

# 12. Inference

Inference

=

Deriving

new facts

from

existing facts.

---

Example

```
Rain

Rain → Wet

↓

Wet
```

---

# 13. Common Exam MCQs

✔ Knowledge Base stores

→ Facts

Rules

---

✔ Model

→ Assignment of Truth Values

---

✔ Conjunction

→ Both True

---

✔ Disjunction

→ At least one True

---

✔ Negation

→ Opposite Truth Value

---

✔ Implication

→ False only when

True → False

---

✔ Entailment

→ Logical Consequence

---

✔ Logical Agent

→ Uses Knowledge Base

and

Inference.

---

# 14. Memory Tricks

```
NOT

↓

Opposite
```

```
AND

↓

Both
```

```
OR

↓

At Least One
```

```
IF

↓

Implication
```

```
IFF

↓

Same
```

---

# One-Page Revision

```
Logical Agent
=============
KB
Inference

Knowledge Base
==============
Facts
Rules

Connectives
============
NOT

AND

OR

→

↔

Model
=====
Truth Assignment

Entailment
==========
KB ⊨ α

Inference
=========
New Facts
```

---
# Chapter 7 – Logical Agents

# Part 2 – First-Order Logic (FOL) & Inference

*(Exam Revision Notes based on AIMA 4th Edition)*

---

# Learning Objectives

After studying this chapter, you should be able to:

* Explain First-Order Logic (FOL)
* Differentiate FOL from Propositional Logic
* Understand predicates, variables, constants, and functions
* Explain quantifiers
* Understand unification
* Explain forward and backward chaining
* Understand resolution

---

# 1. Why First-Order Logic?

Propositional Logic can only represent complete facts.

Example

```text
It is raining.
```

It **cannot** express relationships like:

```text
All students study.
```

or

```text
Every bird can fly.
```

To represent such relationships, AI uses **First-Order Logic (FOL)**.

---

# 2. First-Order Logic (FOL) ⭐⭐⭐⭐⭐

FOL extends propositional logic by introducing:

* Objects
* Predicates
* Variables
* Quantifiers
* Functions

It is much more expressive.

---

# Example

Instead of writing

```text
Student1 Studies

Student2 Studies

Student3 Studies
```

Write

```text
Studies(x)
```

where **x** can represent any student.

---

# 3. Components of FOL ⭐⭐⭐⭐⭐

## Constants

Represent specific objects.

Examples

```text
Ram

Delhi

India

Earth
```

---

## Variables

Represent unknown objects.

Examples

```text
x

y

z
```

---

## Predicates

Represent relationships or properties.

Examples

```text
Student(x)

Parent(x,y)

Loves(x,y)

Bird(x)
```

Predicates evaluate to **True** or **False**.

---

## Functions

Return an object.

Examples

```text
Father(John)

Age(Ram)

Capital(India)
```

---

# 4. Universal Quantifier (∀) ⭐⭐⭐⭐⭐

Symbol

```text
∀
```

Meaning

> **For every object**

---

Example

```text
∀x Bird(x) → Fly(x)
```

Meaning

Every bird flies.

---

This appeared directly in your PT.

Correct answer:

✔ The rule applies to **every object**.

---

# 5. Existential Quantifier (∃) ⭐⭐⭐⭐⭐

Symbol

```text
∃
```

Meaning

> **There exists at least one object**

---

Example

```text
∃x Student(x)
```

Meaning

There exists at least one student.

---

# Universal vs Existential

| Universal    | Existential         |
| ------------ | ------------------- |
| ∀            | ∃                   |
| Every object | At least one object |

---

# 6. Example of FOL

Knowledge Base

```text
∀x Human(x) → Mortal(x)

Human(Socrates)
```

Inference

```text
Mortal(Socrates)
```

---

# 7. Why is FOL Better?

Example

Propositional Logic

```text
Human1

Human2

Human3
```

Need many statements.

---

FOL

```text
∀x Human(x) → Mortal(x)
```

One statement.

Much more expressive.

---

# 8. Limitations of Propositional Logic ⭐⭐⭐⭐⭐

This appeared in your PT.

Correct Answer

✔ Lacks variables and quantifiers.

Other limitations

* Cannot represent relationships.
* Cannot express "all" or "some."
* Large knowledge bases become repetitive.

---

# 9. Unification ⭐⭐⭐⭐

Definition

Process of making two logical expressions identical by finding substitutions.

---

Example

```text
Parent(x,Ram)

Parent(John,Ram)
```

Substitution

```text
x = John
```

Expressions become identical.

---

# 10. Inference in FOL ⭐⭐⭐⭐⭐

Inference means deriving new facts.

Example

Knowledge

```text
∀x Human(x) → Mortal(x)

Human(Ram)
```

Infer

```text
Mortal(Ram)
```

---

# 11. Forward Chaining ⭐⭐⭐⭐⭐

Starts with known facts.

Applies rules.

Produces new facts.

```text
Facts

↓

Rules

↓

New Facts

↓

Goal
```

---

Example

```text
Rain

Rain→Wet

↓

Wet
```

---

Characteristics

✔ Data-driven

✔ Starts from facts

✔ Good for expert systems

---

# 12. Backward Chaining ⭐⭐⭐⭐⭐

Starts with goal.

Looks for rules.

Works backwards.

```text
Goal

↓

Rule

↓

Facts
```

---

Example

Goal

```text
Wet?
```

Check

```text
Rain→Wet
```

Need

```text
Rain
```

Found

Goal proved.

---

Characteristics

✔ Goal-driven

✔ Used in diagnosis

✔ Used in Prolog

---

# Forward vs Backward Chaining

| Forward                   | Backward             |
| ------------------------- | -------------------- |
| Data Driven               | Goal Driven          |
| Starts with facts         | Starts with goal     |
| Generates all conclusions | Finds required proof |

---

# 13. Resolution ⭐⭐⭐⭐

A rule of inference.

Used in theorem proving.

Idea

Combine clauses

↓

Produce new clause.

If contradiction found

↓

Statement proved.

---

Example

```text
P∨Q

¬P

↓

Q
```

---

# 14. Knowledge Representation Languages

Examples

* Propositional Logic
* First-Order Logic
* Semantic Networks
* Frames
* Ontologies

---

# 15. Frequently Asked MCQs

✔ Universal Quantifier

→ Every object

---

✔ Existential Quantifier

→ At least one object

---

✔ FOL uses

→ Variables

Predicates

Quantifiers

---

✔ Propositional Logic cannot

→ Use variables and quantifiers

---

✔ Forward Chaining

→ Data Driven

---

✔ Backward Chaining

→ Goal Driven

---

✔ Resolution

→ Inference Rule

---

✔ Predicate

→ Represents relationships

---

# 16. Memory Tricks

```text
∀

↓

All
```

---

```text
∃

↓

Exists
```

---

```text
Forward

↓

Facts

↓

Goal
```

---

```text
Backward

↓

Goal

↓

Facts
```

---

# 17. Common 2-Mark Questions

### Define First-Order Logic.

First-Order Logic is an extension of propositional logic that uses predicates, variables, constants, functions, and quantifiers to represent objects and relationships.

---

### What is a predicate?

A predicate is a logical expression representing a property or relationship among objects.

---

### Differentiate Universal and Existential Quantifiers.

* Universal (∀): Applies to every object.
* Existential (∃): Applies to at least one object.

---

### Differentiate Forward and Backward Chaining.

* Forward Chaining starts from known facts and derives conclusions.
* Backward Chaining starts from the goal and works backward to verify supporting facts.

---

# 18. One-Page Revision Sheet

```text
First Order Logic
=================
Objects
Predicates
Variables
Functions
Quantifiers

Constants
=========
Ram
Delhi

Variables
=========
x
y

Predicate
=========
Student(x)

Parent(x,y)

Universal
=========
∀

Every Object

Existential
===========
∃

At Least One

Forward Chaining
================
Facts → Goal

Backward Chaining
=================
Goal → Facts

Resolution
==========
Inference Rule

PL Limitation
=============
No Variables
No Quantifiers
```

---
