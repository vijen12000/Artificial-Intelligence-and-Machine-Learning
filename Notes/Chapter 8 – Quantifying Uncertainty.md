## Part 1 – Probability Fundamentals

---

# Learning Objectives

After this chapter you should be able to:

* Explain uncertainty in AI
* Define probability
* Differentiate deterministic and probabilistic reasoning
* Understand conditional probability
* Explain Bayes' Theorem
* Understand independence
* Explain probabilistic inference

---

# 1. Why Do We Need Uncertainty? ⭐⭐⭐⭐⭐

Not every AI problem has complete information.

Examples

* Weather prediction
* Medical diagnosis
* Stock market
* Speech recognition
* Self-driving cars

Instead of certainty,

AI uses

Probability.

---

# 2. Deterministic vs Probabilistic Systems ⭐⭐⭐⭐⭐

| Deterministic            | Probabilistic      |
| ------------------------ | ------------------ |
| Same input → Same output | Output uncertain   |
| No randomness            | Randomness present |
| Chess                    | Weather            |
| Calculator               | Medical diagnosis  |

---

Example

Weather

```text
Rain Tomorrow
```

Not

100%

Instead

```text
70%
```

---

# 3. Probability ⭐⭐⭐⭐⭐

Probability measures

How likely

an event is.

Range

Where

0

Impossible

1

Certain

---

Example

```text
P(Rain)=0.8
```

Means

80% chance

of rain.

---

# 4. Events

Event

=

Outcome

Example

```text
Rolling Dice
```

Event

```text
Get 6
```

---

# 5. Sample Space

Set of

All possible outcomes.

Example

Dice

```text
{1,2,3,4,5,6}
```

---

# 6. Conditional Probability ⭐⭐⭐⭐⭐

Probability

of A

given B.

Notation

Meaning

Probability of

A

assuming

B

has already happened.

---

Example

Probability

of rain

given

clouds.

---

# Formula

---

# 7. Joint Probability ⭐⭐⭐⭐

Probability

that

both events

occur.

Notation

Example

Rain

AND

Traffic.

---

# 8. Independence ⭐⭐⭐⭐⭐

Two events

are independent

if one

does not affect

the other.

Formula

---

Example

Coin Toss

and

Rolling Dice.

Independent.

---

# 9. Bayes' Theorem ⭐⭐⭐⭐⭐

One of the

most important

equations in AI.

---

Meaning

Update belief

after

new evidence.

---

Example

Disease Diagnosis

Before Test

↓

10%

After Positive Test

↓

95%

Belief

changes

using

Bayes' Rule.

---

Applications

* Medical diagnosis
* Spam filtering
* Face recognition
* Speech recognition

---

# 10. Prior Probability

Belief

Before

seeing evidence.

Example

```text
Disease

10%
```

---

# 11. Posterior Probability

Belief

After

seeing evidence.

Example

Positive Test

↓

Disease

95%

---

# 12. Likelihood

Probability

of evidence

assuming

hypothesis

is true.

Example

```text
P(Test Positive | Disease)
```

---

# 13. Probabilistic Inference ⭐⭐⭐⭐⭐

Using probability

to answer

questions.

Instead of

certain

answers,

AI computes

Most likely answer.

---

Example

Robot

hears sound.

Probability

Door Open

↓

80%

---

# 14. Why Probability is Better Than Logic?

Logic

```text
Rain

or

No Rain
```

Probability

```text
70% Rain
```

Much closer

to

real life.

---

# 15. Applications

* Weather Forecasting
* Medical Diagnosis
* Autonomous Vehicles
* Robotics
* Finance
* Recommendation Systems
* Fraud Detection

---

# 16. Frequently Asked MCQs

✔ Probability lies between

→ **0 and 1**

---

✔ Conditional probability means

→ **Probability given evidence**

---

✔ Bayes' Theorem updates

→ **Belief after evidence**

---

✔ Independent events satisfy

→ **P(A∩B)=P(A)P(B)**

---

✔ Prior probability

→ **Before evidence**

---

✔ Posterior probability

→ **After evidence**

---

✔ Probabilistic reasoning

→ **Reasoning under uncertainty**

---

# 17. Memory Tricks

```text
Prior

↓

Before
```

---

```text
Posterior

↓

After
```

---

```text
Conditional

↓

Given
```

---

```text
Bayes

↓

Update Belief
```

---

# 18. Frequently Asked 2-Mark Questions

### Define Probability.

Probability is a numerical measure of the likelihood of an event occurring, ranging from 0 (impossible) to 1 (certain).

---

### Define Conditional Probability.

Conditional probability is the probability of an event occurring given that another event has already occurred.

---

### State Bayes' Theorem.

Bayes' Theorem updates the probability of a hypothesis after observing new evidence.

---

### Differentiate Prior and Posterior Probability.

* **Prior Probability:** Belief before observing evidence.
* **Posterior Probability:** Updated belief after observing evidence.

---

# One-Page Revision Sheet

```text
Uncertainty
===========
Probability

Probability
===========
0 ≤ P(A) ≤ 1

Conditional
===========
P(A|B)

Joint
=====
P(A∩B)

Independent
===========
P(A∩B)=P(A)P(B)

Bayes
======
Update Belief

Prior
=====
Before Evidence

Posterior
=========
After Evidence

Applications
============
Weather
Medicine
Robotics
Finance
```

---
