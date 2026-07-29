# Learning Objectives

After this chapter you should be able to:

* Define an agent
* Explain agent function and agent program
* Define rationality
* Explain PEAS
* Classify task environments
* Describe different types of intelligent agents
* Understand learning agents

---

# 1. What is an Agent?

An **agent** is anything that:

* Perceives its environment using **sensors**
* Acts upon the environment using **actuators**

This is the fundamental definition used throughout the book. 

### General Structure

```text
Environment
      │
      ▼
  Sensors
      │
      ▼
    Agent
      │
      ▼
 Actuators
      │
      ▼
Environment
```

---

## Examples

| Agent            | Sensors               | Actuators                     |
| ---------------- | --------------------- | ----------------------------- |
| Human            | Eyes, ears, nose      | Hands, legs, mouth            |
| Robot            | Camera, LIDAR, GPS    | Wheels, robotic arms          |
| Self-driving Car | Cameras, Radar, LIDAR | Steering, brakes, accelerator |
| ChatGPT          | User prompts          | Generated text                |
| Web Crawler      | Web pages             | Downloads/indexes pages       |

---

# 2. Agent Function

The **Agent Function** maps:

> Percept Sequence → Action

```text
Percepts
      ↓
Agent Function
      ↓
Action
```

The agent function describes the ideal behavior.

---

# 3. Agent Program

The **Agent Program** is the actual software implementation that runs on hardware to realize the agent function. 

| Agent Function          | Agent Program            |
| ----------------------- | ------------------------ |
| Mathematical definition | Actual code              |
| Abstract                | Practical implementation |

---

# 4. Rational Agent

A **rational agent** selects the action expected to maximize its performance measure based on:

* the percept history,
* its built-in knowledge,
* the actions available,
* and what it has learned.

---

## Rational ≠ Omniscient

### Rational

Makes the **best possible decision** with available information.

### Omniscient

Knows everything, including future events.

AI agents are expected to be **rational**, **not omniscient**.

---

Example:

Weather forecast:

```
70% chance of rain
```

Taking an umbrella is rational even if it ultimately does not rain.

---

# 5. Performance Measure

A performance measure defines what counts as success for an agent.

Examples:

Robot Vacuum:

* Dirt removed
* Electricity saved
* Time consumed
* Battery usage

Self-driving Car:

* Passenger safety
* Reaches destination
* Obeys traffic rules
* Fuel efficiency

Chess Agent:

* Win the game

---

# 6. PEAS

One of the most important exam topics.

PEAS stands for:

* **P** – Performance Measure
* **E** – Environment
* **A** – Actuators
* **S** – Sensors

PEAS helps specify an intelligent agent before designing it. 

---

## Example 1 – Self-Driving Car

| Component   | Description                   |
| ----------- | ----------------------------- |
| Performance | Safe, fast, legal driving     |
| Environment | Roads, pedestrians, weather   |
| Actuators   | Steering, accelerator, brakes |
| Sensors     | Cameras, GPS, Radar, LIDAR    |

---

## Example 2 – Chess Agent

| Component   | Description       |
| ----------- | ----------------- |
| Performance | Win the game      |
| Environment | Chess board       |
| Actuators   | Move chess pieces |
| Sensors     | Board state       |

---

## Example 3 – Medical Diagnosis System

| Component   | Description                 |
| ----------- | --------------------------- |
| Performance | Accurate diagnosis          |
| Environment | Patients, hospitals         |
| Actuators   | Diagnostic reports          |
| Sensors     | Symptoms, lab tests, X-rays |

---

# 7. Task Environment

A task environment describes the conditions in which an agent operates.

Task environments can be classified along several important dimensions. 

---

## A. Fully Observable vs Partially Observable

### Fully Observable

Agent has complete information.

Example:

Chess

---

### Partially Observable

Some information is hidden.

Example:

Poker

Self-driving car

Medical diagnosis

---

## B. Deterministic vs Stochastic

### Deterministic

Same action → Same result.

Example:

Chess

Sudoku

---

### Stochastic

Actions have uncertain outcomes.

Example:

Driving

Medical treatment

Weather prediction

---

## C. Episodic vs Sequential

### Episodic

Each decision is independent.

Example:

Spam filtering

Image classification

---

### Sequential

Current decisions affect future decisions.

Example:

Chess

Driving

Robot navigation

---

## D. Static vs Dynamic

### Static

Environment doesn't change while the agent thinks.

Example:

Crossword puzzle

---

### Dynamic

Environment changes continuously.

Example:

Traffic

Stock market

Robotics

---

## E. Discrete vs Continuous

### Discrete

Finite states and actions.

Example:

Chess

Tic-Tac-Toe

---

### Continuous

Infinite possible values.

Example:

Car steering angle

Robot arm movement

Temperature control

---

## F. Single Agent vs Multi-Agent

### Single Agent

Only one intelligent agent.

Example:

Sudoku solver

---

### Multi-Agent

Multiple interacting agents.

Example:

Chess

Football robots

Autonomous vehicles

---

## G. Known vs Unknown

### Known

Rules are already known.

Example:

Chess

---

### Unknown

The agent must learn how the environment behaves.

Example:

Exploring a new planet

---

# Quick Summary Table

| Property      | Option 1      | Option 2   |
| ------------- | ------------- | ---------- |
| Observability | Fully         | Partially  |
| Outcome       | Deterministic | Stochastic |
| Decision      | Episodic      | Sequential |
| Environment   | Static        | Dynamic    |
| Values        | Discrete      | Continuous |
| Agents        | Single        | Multi      |
| Model         | Known         | Unknown    |

---

# Exam Questions

### 2 Marks

* Define an intelligent agent.
* What is a rational agent?
* Expand PEAS.
* What is an actuator?

### 5 Marks

* Explain PEAS with an example.
* Differentiate between agent function and agent program.
* Explain rationality in AI.

### 10 Marks

* Explain the dimensions of task environments with suitable examples.

---

# 8. Types of Intelligent Agents ⭐⭐⭐⭐⭐

There are **five major agent architectures**:

1. Simple Reflex Agent
2. Model-Based Reflex Agent
3. Goal-Based Agent
4. Utility-Based Agent
5. Learning Agent

Think of them as increasing levels of intelligence.

```text
Simple Reflex
       ↓
Model-Based Reflex
       ↓
Goal-Based
       ↓
Utility-Based
       ↓
Learning Agent
```

---

# 9. Simple Reflex Agent ⭐⭐⭐⭐

## Definition

A Simple Reflex Agent chooses actions **only from the current percept**.

It does **not remember the past**.

### Structure

```text
Percept
   ↓
Condition-Action Rule
   ↓
Action
```

Example Rule

```text
IF room is dirty
THEN suck
```

Vacuum Cleaner

```text
IF Dirty
      ↓
Suck

IF Clean
      ↓
Move
```

---

## Characteristics

✅ Fast

✅ Simple

❌ No memory

❌ Cannot handle partially observable environments

❌ Cannot learn

---

## Suitable Environment

* Fully observable
* Deterministic
* Static

---

# 10. Model-Based Reflex Agent ⭐⭐⭐⭐⭐

A Simple Reflex Agent fails when it cannot observe everything.

A Model-Based Reflex Agent solves this by maintaining an **internal model (state)** of the world.

---

### Structure

```text
Percepts
      ↓
Internal State
      ↓
World Model
      ↓
Rules
      ↓
Action
```

---

Example

Robot Vacuum

Robot cannot see Room B.

It remembers:

```text
Yesterday
Room B was dirty
```

Internal state stores this information.

---

## Characteristics

✔ Has memory

✔ Tracks hidden information

✔ Better for partially observable environments

---

# Simple Reflex vs Model-Based

| Simple               | Model-Based          |
| -------------------- | -------------------- |
| No memory            | Has memory           |
| Current percept only | Uses history         |
| Fully observable     | Partially observable |

---

# 11. Goal-Based Agent ⭐⭐⭐⭐⭐

Instead of simply reacting,

the agent asks:

> **"Which action will help me achieve my goal?"**

---

### Structure

```text
Percepts
      ↓
Current State
      ↓
Goal
      ↓
Search
      ↓
Best Action
```

---

Example

GPS Navigation

Goal

```text
Reach Airport
```

GPS searches possible routes before choosing.

---

Characteristics

✔ Uses Search

✔ Uses Planning

✔ Flexible

✔ Better decision making

---

Disadvantage

Planning may take time.

---

# 12. Utility-Based Agent ⭐⭐⭐⭐⭐

Sometimes multiple goals exist.

Example

Driving

Goal:

Reach destination.

But also

* Safe
* Comfortable
* Fuel Efficient

How do we choose?

Use a **Utility Function**. 

---

Utility

A numerical value representing how desirable a state is.

Higher Utility

=

Better State

---

Structure

```text
State
      ↓
Possible Actions
      ↓
Expected Utility
      ↓
Choose Maximum
```

---

Example

Route A

```text
20 min
Unsafe
```

Utility = 60

Route B

```text
25 min
Very Safe
```

Utility = 95

Choose

Route B

---

Characteristics

✔ Handles trade-offs

✔ Deals with uncertainty

✔ Chooses best expected outcome

---

Exam Definition

> A Utility-Based Agent selects the action with the **highest expected utility**. 

---

# 13. Learning Agent ⭐⭐⭐⭐⭐

The most advanced architecture.

A Learning Agent improves over time through experience.

---

Structure

```text
Environment
      ↓
Performance Element
      ↓
Critic
      ↓
Learning Element
      ↓
Problem Generator
      ↓
Improved Performance
```

## Components

### Performance Element

Actually performs the task.

---

### Learning Element

Improves behavior.

---

### Critic

Provides feedback.

---

### Problem Generator

Suggests exploratory actions.

---

Example

AlphaGo

Initially weak

↓

Plays millions of games

↓

Learns better strategies

↓

Becomes World Champion

---

Examples

* ChatGPT
* AlphaGo
* Self-driving Cars
* Recommendation Systems

---

# 14. Comparison of Agent Types ⭐⭐⭐⭐⭐

| Agent         | Memory | Goal | Utility | Learning |
| ------------- | ------ | ---- | ------- | -------- |
| Simple Reflex | ❌      | ❌    | ❌       | ❌        |
| Model-Based   | ✔      | ❌    | ❌       | ❌        |
| Goal-Based    | ✔      | ✔    | ❌       | ❌        |
| Utility-Based | ✔      | ✔    | ✔       | ❌        |
| Learning      | ✔      | ✔    | ✔       | ✔        |

**Memory trick:** each new architecture adds one new capability.

---

# 15. Which Agent Should Be Used?

| Problem          | Agent          |
| ---------------- | -------------- |
| Thermostat       | Simple Reflex  |
| Vacuum Cleaner   | Model-Based    |
| GPS              | Goal-Based     |
| Self-driving Car | Utility-Based  |
| ChatGPT          | Learning Agent |

---

# 16. Complete Flow of AI Agent Development

```text
Sensors
      ↓
Percepts
      ↓
Internal State
      ↓
Goal
      ↓
Utility
      ↓
Learning
      ↓
Action
```

---

# 17. Frequently Asked Comparisons

## Goal-Based vs Utility-Based

| Goal           | Utility            |
| -------------- | ------------------ |
| Reach goal     | Reach best goal    |
| No preferences | Has preferences    |
| Simpler        | More flexible      |
| No trade-offs  | Handles trade-offs |

---

## Utility vs Learning

| Utility                | Learning                 |
| ---------------------- | ------------------------ |
| Fixed utility function | Improves with experience |
| No learning            | Learns continuously      |

---

## Reflex vs Goal-Based

| Reflex             | Goal              |
| ------------------ | ----------------- |
| Immediate response | Planning required |
| Rule based         | Search based      |

---

# 18. Exam MCQs ⭐⭐⭐⭐⭐

Know these well:

* Which agent has **no memory**? → **Simple Reflex**
* Which agent maintains an **internal state**? → **Model-Based Reflex**
* Which agent uses **search**? → **Goal-Based**
* Which agent uses **expected utility**? → **Utility-Based**
* Which agent contains a **Critic**? → **Learning Agent**
* Which agent **improves with experience**? → **Learning Agent**

---

# 19. Common Interview Questions

### What is the difference between Goal-Based and Utility-Based Agents?

A goal-based agent only tries to achieve a goal, whereas a utility-based agent evaluates all possible outcomes and chooses the one with the highest expected utility.

---

### Why is a Utility-Based Agent better?

Because it can:

* Handle conflicting goals.
* Make decisions under uncertainty.
* Choose the most desirable outcome, not just any goal state.

---

### Why do Learning Agents perform better?

Because they improve over time by using feedback from their environment.

---

# 20. One-Page Revision Sheet

```text
Agent
=====
Perceives → Sensors
Acts → Actuators

PEAS
====
Performance
Environment
Actuators
Sensors

Task Environment
================
Fully / Partially Observable
Deterministic / Stochastic
Episodic / Sequential
Static / Dynamic
Discrete / Continuous
Single / Multi-Agent
Known / Unknown

Agent Types
===========
1. Simple Reflex
2. Model-Based Reflex
3. Goal-Based
4. Utility-Based
5. Learning

Simple
------
No Memory

Model
-----
Internal State

Goal
----
Search + Planning

Utility
-------
Expected Utility

Learning
--------
Performance Element
Learning Element
Critic
Problem Generator
```

## Exam Focus (DA109)

Based on your syllabus and the emphasis in AIMA, prioritize these topics:

| Topic                           | Importance |
| ------------------------------- | ---------- |
| Agent definition                | ⭐⭐⭐⭐⭐      |
| Rational agent                  | ⭐⭐⭐⭐⭐      |
| PEAS                            | ⭐⭐⭐⭐⭐      |
| Task environment properties     | ⭐⭐⭐⭐⭐      |
| Agent architectures             | ⭐⭐⭐⭐⭐      |
| Utility-based agents            | ⭐⭐⭐⭐       |
| Learning agent components       | ⭐⭐⭐⭐       |
| Comparisons between agent types | ⭐⭐⭐⭐⭐      |



