# Part 1 – Introduction to Machine Learning

*(Exam Revision Notes for DA109)*

This chapter corresponds directly to:

> **Introduction to Learning**
>
> * Supervised Learning
> * Unsupervised Learning
> * Reinforcement Learning

---

# Learning Objectives

After studying this chapter you should be able to:

* Define Machine Learning
* Explain types of learning
* Differentiate supervised, unsupervised and reinforcement learning
* Understand datasets
* Explain training and testing
* Explain classification and regression

---

# 1. What is Machine Learning? ⭐⭐⭐⭐⭐

Machine Learning (ML) is a branch of AI in which computers **learn patterns from data** and improve their performance without being explicitly programmed.

Instead of writing rules,

```text
Input

↓

Program

↓

Output
```

Machine Learning

```text
Data

↓

Learning Algorithm

↓

Model

↓

Prediction
```

---

# 2. AI vs Machine Learning ⭐⭐⭐⭐⭐

| Artificial Intelligence              | Machine Learning |
| ------------------------------------ | ---------------- |
| Broad field                          | Subfield of AI   |
| Includes search, planning, reasoning | Learns from data |
| Rule based or learning based         | Data driven      |

---

# 3. Why Machine Learning?

Traditional programming

```text
Rules + Data

↓

Answer
```

Machine Learning

```text
Data + Answers

↓

Learns Rules
```

---

Applications

* Spam Detection
* Face Recognition
* Recommendation Systems
* Fraud Detection
* Voice Assistants

---

# 4. Types of Learning ⭐⭐⭐⭐⭐

Three major categories

```text
Machine Learning

↓

Supervised

↓

Unsupervised

↓

Reinforcement
```

---

# 5. Supervised Learning ⭐⭐⭐⭐⭐

Definition

The algorithm learns using

**labelled data**.

Training data contains

Inputs

and

Correct Outputs.

---

Example

Emails

```text
Spam

Not Spam
```

Algorithm learns

Future emails.

---

Examples

* Disease Prediction
* House Price Prediction
* Credit Approval
* Image Classification

---

# 6. Components of Supervised Learning

Training Data

↓

Learning Algorithm

↓

Model

↓

Prediction

---

# 7. Classification ⭐⭐⭐⭐⭐

Output

belongs

to a category.

Examples

```text
Spam

Not Spam
```

```text
Cat

Dog
```

```text
Approved

Rejected
```

---

# 8. Regression ⭐⭐⭐⭐⭐

Output

is a

continuous value.

Examples

```text
House Price

₹58,00,000
```

```text
Temperature

35°C
```

---

# Classification vs Regression

| Classification | Regression      |
| -------------- | --------------- |
| Category       | Numerical Value |
| Spam           | House Price     |
| Disease        | Temperature     |

---

# 9. Training Data ⭐⭐⭐⭐⭐

Used to

teach

the model.

Example

```text
Height

Weight

Disease
```

---

# 10. Testing Data ⭐⭐⭐⭐⭐

Used

after training

to evaluate

performance.

Never used

during training.

---

# 11. Model

A Model

is the learned function

that makes predictions.

---

Example

```text
Student Marks

↓

Model

↓

Pass
```

---

# 12. Features

Features

=

Input Variables.

Example

House Price

Features

```text
Area

Bedrooms

Location
```

---

# 13. Labels

Correct answers

for supervised learning.

Example

```text
Email

↓

Spam
```

Spam

=

Label.

---

# 14. Workflow

```text
Collect Data

↓

Clean Data

↓

Train Model

↓

Test Model

↓

Deploy Model
```

---

# 15. Advantages of Supervised Learning

✔ High Accuracy

✔ Easy Evaluation

✔ Widely Used

---

# 16. Disadvantages

Needs

Large labelled datasets.

Labelling

is expensive.

---

# 17. Frequently Asked MCQs

Supervised Learning uses

✅ Labelled Data

---

Spam Detection

is

✅ Classification

---

House Price Prediction

is

✅ Regression

---

Training data

is used for

✅ Learning

---

Testing data

is used for

✅ Evaluation

---

# 18. Memory Tricks

```text
Supervised

↓

Teacher
```

---

```text
Classification

↓

Category
```

---

```text
Regression

↓

Number
```

---

# One-Page Revision

```text
Machine Learning
================
Learn From Data

Supervised
===========
Labelled Data

Classification
==============
Category

Regression
==========
Number

Training
========
Learn

Testing
========
Evaluate

Features
========
Inputs

Labels
======
Correct Outputs
```

---
# 1. Unsupervised Learning ⭐⭐⭐⭐⭐

## Definition

In Unsupervised Learning, the algorithm learns from **unlabeled data**.

Unlike supervised learning, there are **no correct answers** provided during training.

```text
Input Data
     ↓
Learning Algorithm
     ↓
Patterns / Groups
```

---

## Example

Customer purchase data:

| Customer | Age | Income |
| -------- | --- | ------ |
| A        | 24  | 35K    |
| B        | 26  | 38K    |
| C        | 52  | 90K    |

The algorithm automatically discovers groups of similar customers.

---

## Applications

* Customer Segmentation
* Market Basket Analysis
* Fraud Detection
* Recommendation Systems
* Anomaly Detection

---

# 2. Clustering ⭐⭐⭐⭐⭐

The most common unsupervised learning task.

Definition:

> Group similar data points into clusters.

Example

```text
Students

↓

High Performers

Average Performers

Needs Improvement
```

The groups are **not pre-labeled**.

---

## Popular Clustering Algorithms

* K-Means
* Hierarchical Clustering
* DBSCAN (advanced)

For DA109, knowing **K-Means** is usually sufficient.

---

# 3. Supervised vs Unsupervised ⭐⭐⭐⭐⭐

| Supervised        | Unsupervised      |
| ----------------- | ----------------- |
| Labelled data     | Unlabelled data   |
| Teacher available | No teacher        |
| Classification    | Clustering        |
| Regression        | Pattern Discovery |

---

# 4. Reinforcement Learning (RL) ⭐⭐⭐⭐⭐

Definition:

An agent learns by **interacting with an environment** and receiving rewards or penalties.

```text
Agent
   ↓ Action
Environment
   ↓ Reward
Agent
```

The objective is to maximize the **total reward** over time.

---

# 5. RL Components ⭐⭐⭐⭐⭐

## Agent

The learner.

Examples:

* Robot
* Self-driving car
* Chess program

---

## Environment

Everything outside the agent.

Examples:

* Chess board
* Road
* Video game
* Warehouse

---

## Action

A decision taken by the agent.

Examples:

* Move Left
* Accelerate
* Pick Object

---

## State

The current situation of the environment.

Example:

Robot at Room A.

---

## Reward ⭐⭐⭐⭐⭐

A numerical feedback signal.

Example:

```text
Reach Goal

Reward = +100
```

```text
Hit Obstacle

Reward = -50
```

The agent tries to maximize cumulative reward.

---

# 6. Policy ⭐⭐⭐⭐

A **policy** tells the agent which action to choose in each state.

Notation:

```text
π(s)
```

Meaning:

Action chosen in state **s**.

---

# 7. Exploration vs Exploitation ⭐⭐⭐⭐⭐

One of the most important RL concepts.

### Exploration

Try new actions to gather information.

Example:

Trying a new restaurant.

---

### Exploitation

Choose the action known to give the highest reward.

Example:

Going to your favorite restaurant.

---

Good RL balances **exploration** and **exploitation**.

---

# 8. Multi-Armed Bandit (MAB) ⭐⭐⭐⭐⭐

This topic directly relates to your recent quizzes.

Imagine several slot machines.

```text
🎰 🎰 🎰 🎰
```

Each machine has an unknown probability of reward.

Goal:

Find the machine with the highest expected reward.

---

## Challenge

Should you:

* Explore new machines?
* Exploit the best one found so far?

This is exactly the **exploration vs exploitation** trade-off.

---

# 9. ε-Greedy Strategy ⭐⭐⭐⭐⭐

With probability **ε**:

→ Explore.

With probability **1 − ε**:

→ Exploit.

Example:

ε = 0.2

* 20% Explore
* 80% Exploit

This matches the quiz question you solved.

---

# 10. Decaying ε (εₜ-Greedy)

Instead of a fixed ε,

reduce exploration over time.

Example:

Initially:

Lots of exploration.

Later:

Mostly exploitation.

This is why **εₜ-greedy** generally performs better than fixed ε-greedy.

---

# 11. Regret ⭐⭐⭐⭐

Regret measures the loss incurred by not always selecting the optimal action.

Lower regret = Better algorithm.

Algorithms like εₜ-greedy are designed to achieve **logarithmic regret** under appropriate assumptions.

---

# 12. Q-Learning (Introduction)

Q-Learning is a reinforcement learning algorithm.

It learns the expected value of taking an action in a given state.

Conceptually:

```text
State

↓

Action

↓

Reward

↓

Update Knowledge
```

(DA109 usually requires only the concept, not the update equation.)

---

# 13. Applications of RL

* Robotics
* Game Playing (AlphaGo)
* Autonomous Vehicles
* Resource Allocation
* Industrial Control
* Recommendation Systems

---

# 14. Comparison of Learning Types ⭐⭐⭐⭐⭐

| Feature  | Supervised     | Unsupervised          | Reinforcement   |
| -------- | -------------- | --------------------- | --------------- |
| Labels   | Yes            | No                    | No              |
| Feedback | Immediate      | None                  | Reward          |
| Goal     | Predict        | Discover Patterns     | Maximize Reward |
| Example  | Spam Detection | Customer Segmentation | Chess AI        |

---

# 15. Common Exam MCQs

✔ Supervised Learning uses

→ **Labelled Data**

---

✔ Unsupervised Learning uses

→ **Unlabelled Data**

---

✔ Reinforcement Learning learns using

→ **Rewards and penalties**

---

✔ K-Means is

→ **Clustering Algorithm**

---

✔ MAB belongs to

→ **Online Learning / Reinforcement Learning setting**

---

✔ ε-Greedy balances

→ **Exploration and Exploitation**

---

✔ Reward is provided by

→ **Environment**

---

✔ Agent aims to maximize

→ **Cumulative Reward**

---

# 16. Memory Tricks

```text
Supervised

↓

Teacher
```

```text
Unsupervised

↓

Find Groups
```

```text
Reinforcement

↓

Trial + Reward
```

```text
Explore

↓

Learn
```

```text
Exploit

↓

Earn
```

---

# One-Page Revision

```text
Machine Learning
================
Supervised
Unsupervised
Reinforcement

Supervised
===========
Labels

Classification
Regression

Unsupervised
=============
No Labels

Clustering

Reinforcement
=============
Agent
Environment
Action
State
Reward
Policy

MAB
===
Explore
Exploit

ε-Greedy
========
Explore = ε
Exploit = 1−ε

Goal
====
Maximum Reward
```

---

# Complete Learning Summary

```text
Machine Learning

├── Supervised
│     ├── Classification
│     └── Regression
│
├── Unsupervised
│     └── Clustering
│
└── Reinforcement
      ├── Agent
      ├── Environment
      ├── Reward
      ├── Policy
      ├── Exploration
      └── Exploitation
```

---

