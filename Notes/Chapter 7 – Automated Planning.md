## Part 1 – Classical Planning

---

# Learning Objectives

After this chapter you should be able to:

* Define planning
* Explain planning problems
* Differentiate planning and search
* Understand states, operators, actions, and goals
* Explain classical planning assumptions
* Explain forward and backward planning
* Differentiate planning approaches

---

# 1. What is Planning? ⭐⭐⭐⭐⭐

Planning is the process of finding a **sequence of actions** that transforms the **initial state** into the **goal state**.

```text
Initial State
      ↓
Planning
      ↓
Sequence of Actions
      ↓
Goal State
```

Unlike search, planning reasons about **actions and their effects**.

---

# 2. Components of a Planning Problem ⭐⭐⭐⭐⭐

Every planning problem has:

### Initial State

Starting configuration.

Example

```text
Robot at Room A
```

---

### Goal State

Desired configuration.

Example

```text
Robot at Room B
```

---

### Operators (Actions)

Possible actions.

Examples

```text
Move

Pick

Drop
```

This appeared directly in your PT.

Warehouse robot

Move

Pick

Drop

↓

**Operators**

---

### Transition Model

Specifies

```text
Current State

+

Action

↓

Next State
```

---

# 3. State Space

All possible configurations.

Planning searches this state space.

---

# 4. Classical Planning ⭐⭐⭐⭐⭐

Most planning algorithms assume:

✔ Deterministic actions

✔ Fully observable environment

✔ Static environment

✔ Single agent

✔ Known environment

This was one of your PT questions.

Question:

Which assumption is essential?

Answer

✅ **Deterministic Actions**

---

# 5. Deterministic Actions ⭐⭐⭐⭐⭐

Definition

Same action

↓

Always

Same result.

Example

```text
Move Right

↓

Reach Right Cell
```

No randomness.

---

# 6. Forward Planning (Progression Search) ⭐⭐⭐⭐⭐

Start

↓

Initial State

↓

Apply actions

↓

Goal

```text
Start

↓

Action

↓

Action

↓

Goal
```

Your PT asked:

Robot repeatedly applies actions until reaching the goal.

Answer

✅ **Forward Search**

---

# 7. Backward Planning (Regression Planning) ⭐⭐⭐⭐⭐

Instead of starting from the beginning,

start from the goal.

```text
Goal

↓

Previous State

↓

Previous State

↓

Initial State
```

Useful when the goal is well defined.

---

# 8. Forward vs Backward Planning

| Forward        | Backward       |
| -------------- | -------------- |
| Initial → Goal | Goal → Initial |
| Progression    | Regression     |
| Action Driven  | Goal Driven    |

---

# 9. Planning Operators ⭐⭐⭐⭐⭐

Operators define:

* Preconditions
* Action
* Effects

Example

Move(A,B)

Precondition

```text
Robot at A
```

Effect

```text
Robot at B
```

---

# 10. Preconditions

Must be true

before action executes.

Example

```text
Door Open
```

before

```text
Enter Room
```

---

# 11. Effects

Result

after action.

Example

```text
Move(A,B)

↓

Robot at B
```

---

# 12. Intermediate States ⭐⭐⭐⭐

Between

Initial

and

Goal

come

Intermediate States.

This appeared directly in your PT.

Answer

✅ **Intermediate States**

---

# 13. Goal Test

Checks

```text
Current State

=

Goal?
```

Returns

True

or

False.

---

# 14. Planning vs Search ⭐⭐⭐⭐⭐

| Search         | Planning              |
| -------------- | --------------------- |
| Finds path     | Finds action sequence |
| Generic        | Action-oriented       |
| Less knowledge | Uses domain knowledge |

---

# 15. Frequently Asked MCQs

✔ Warehouse robot actions

→ Operators

✔ Between initial and goal

→ Intermediate States

✔ Deterministic planning

→ Same action → Same result

✔ Robot repeatedly executes actions

→ Forward Search

✔ Backward Planning

→ Regression Planning

✔ Planning assumes

→ Deterministic environment

---

# 16. Memory Tricks

```text
Planning

↓

Actions
```

```text
Forward

↓

Start

↓

Goal
```

```text
Backward

↓

Goal

↓

Start
```

```text
Operators

↓

Actions
```

---

# 17. One-Page Revision

```text
Planning
========
Initial State
Goal State
Operators
Actions
Effects

Classical Planning
==================
Deterministic
Static
Fully Observable
Single Agent

Forward Planning
================
Start → Goal

Backward Planning
=================
Goal → Start

Operators
=========
Move
Pick
Drop

Intermediate States
===================
Between Initial & Goal
```

---

# 1. Why Different Planning Methods?

A single planning algorithm cannot solve every problem efficiently.

For example:

* Delivering a package
* Coordinating multiple robots
* Planning a military mission
* Planning a manufacturing process

Each requires a different planning strategy.

---

# 2. Graph Planning ⭐⭐⭐⭐

Graph Planning represents the planning problem as a **Planning Graph**.

The graph alternates between:

```text
State Layer

↓

Action Layer

↓

State Layer

↓

Action Layer
```

---

## Advantages

* Fast planning
* Identifies impossible goals quickly
* Forms the basis of the GraphPlan algorithm

---

## Applications

* Robotics
* Manufacturing
* Scheduling

---

## Exam Point

Graph Planning builds a graph instead of exploring a search tree.

---

# 3. Hierarchical Planning ⭐⭐⭐⭐⭐

Also called

**Hierarchical Task Network (HTN) Planning**

---

## Idea

Break a large problem

↓

Into smaller tasks.

```text
Deliver Package

↓

Reach City

↓

Reach Building

↓

Reach Floor

↓

Deliver
```

---

Example

Mission

↓

Travel

↓

Book Ticket

↓

Board Plane

↓

Reach Destination

Instead of solving everything at once.

---

## Advantages

✔ Easier planning

✔ Better organization

✔ Scalable

---

### PT Question

Which planning type is most suitable for decomposing a complex mission?

✅ **Hierarchical Planning**

---

# 4. Multi-Agent Planning ⭐⭐⭐⭐⭐

Planning involving

Multiple intelligent agents.

Example

```text
Robot A

Robot B

Robot C
```

Need to cooperate.

---

Applications

* Warehouse robots
* Drone fleets
* Traffic control
* Football robots

---

### PT Question

Coordination between several delivery robots mainly requires

✅ **Multi-Agent Planning**

---

# 5. Regression Planning ⭐⭐⭐⭐⭐

Already discussed earlier.

Starts

From Goal

↓

Works backwards.

---

Example

Goal

```text
Robot at Room C
```

Question

What action must occur

immediately before?

Continue until

Initial State.

---

# 6. Classical Planning Review ⭐⭐⭐⭐⭐

Assumptions

✔ Deterministic

✔ Static

✔ Fully Observable

✔ Single Agent

✔ Known Environment

---

# 7. Planning Graph ⭐⭐⭐⭐

Contains

Two alternating layers

```text
States

↓

Actions

↓

States

↓

Actions
```

The graph expands until

Goals become reachable.

---

# 8. Constraints in Planning

Real planning problems contain constraints.

Examples

* Limited fuel
* Battery level
* Time
* Budget
* Resource availability

Planning must satisfy

All constraints.

---

# 9. Planning Under Resource Constraints

Example

Robot

Battery = 20%

Cannot visit

every room.

Planner chooses

Best sequence.

---

# 10. Partial-Order Planning ⭐⭐⭐

Not every action requires a fixed order.

Example

Breakfast

```text
Toast Bread

Boil Eggs
```

Either order is acceptable.

Only requirement

Both complete

Before eating.

---

Advantages

* Flexible
* Efficient
* Allows parallel execution

---

# 11. Comparison of Planning Methods ⭐⭐⭐⭐⭐

| Planning Method        | Best Use                      |
| ---------------------- | ----------------------------- |
| Classical              | Simple deterministic problems |
| Graph Planning         | Efficient action planning     |
| Regression Planning    | Goal-driven problems          |
| Hierarchical Planning  | Large complex missions        |
| Multi-Agent Planning   | Multiple cooperating agents   |
| Partial-Order Planning | Independent tasks             |

---

# 12. Planning Applications ⭐⭐⭐⭐

* Robotics
* Manufacturing
* Logistics
* Navigation
* Space Missions
* Healthcare
* Supply Chain
* Smart Cities

---

# 13. Common MCQs

### Graph Planning uses

✅ Planning Graph

---

### Multi-Agent Planning is used when

✅ Multiple agents cooperate

---

### Hierarchical Planning

✅ Breaks tasks into subtasks

---

### Regression Planning

✅ Goal → Initial State

---

### Classical Planning assumes

✅ Deterministic Environment

---

### Graph Planning expands

✅ States and Actions

---

### Partial-Order Planning

✅ Allows independent actions

---

# 14. Memory Tricks

```text
Graph

↓

GraphPlan
```

---

```text
Hierarchy

↓

Big Task

↓

Small Tasks
```

---

```text
Multi-Agent

↓

Many Robots
```

---

```text
Regression

↓

Goal

↓

Start
```

---

# 15. Frequently Asked 2-Mark Questions

### Define Graph Planning.

Graph Planning represents planning problems using alternating layers of states and actions to efficiently search for a valid plan.

---

### Define Hierarchical Planning.

Hierarchical Planning decomposes a complex task into smaller, manageable subtasks.

---

### Define Multi-Agent Planning.

Multi-Agent Planning coordinates multiple intelligent agents working together toward a common objective.

---

### Define Regression Planning.

Regression Planning starts from the goal state and works backward toward the initial state.

---

# 16. One-Page Revision Sheet

```text
Planning Types
==============

Classical
----------
Deterministic

Graph
------
Planning Graph

Hierarchical
------------
Big → Small Tasks

Regression
-----------
Goal → Start

Multi-Agent
-----------
Multiple Robots

Partial Order
-------------
Flexible Action Order
```

---

# Complete Planning Summary

```text
Planning

↓

Initial State

↓

Operators

↓

Intermediate States

↓

Goal

↓

Planning Techniques

↓

Classical

↓

Graph

↓

Hierarchical

↓

Regression

↓

Multi-Agent

↓

Partial Order
```

---
