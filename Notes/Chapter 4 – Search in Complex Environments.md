## Part 1 – Local Search Algorithms

---

# Learning Objectives

After this chapter you should be able to:

* Explain local search
* Compare local search with graph search
* Explain Hill Climbing
* Explain Simulated Annealing
* Explain Local Beam Search
* Explain Genetic Algorithms
* Compare all local search techniques

---

# 1. Why Local Search?

In Chapter 3, algorithms searched for a **path**.

Sometimes we don't care about the path.

We only care about the **final solution**.

Example:

Finding

* Best timetable
* Best schedule
* Best route
* Best neural network parameters

Only the final answer matters.

---

# 2. Local Search

A local search algorithm:

* Starts with one solution.
* Tries to improve it step by step.
* Stores only the current state.
* Does **not** build a search tree.

```text
Current State
      ↓
Neighbour
      ↓
Better Neighbour
      ↓
Goal
```

---

## Advantages

✔ Very little memory

✔ Fast

✔ Works well for optimization problems

---

## Disadvantages

✘ May get stuck in poor solutions

---

# 3. Hill Climbing ⭐⭐⭐⭐⭐

Hill Climbing is the simplest local search algorithm.

Idea:

> Always move to the neighbouring state that appears better.

Imagine climbing a hill.

```text
          Peak
         /\
        /  \
       /    \
Current
```

Always move uphill.

---

## Algorithm

1. Start from an initial state.
2. Evaluate neighbours.
3. Move to the best neighbour.
4. Repeat until no better neighbour exists.

---

## Advantages

✔ Simple

✔ Fast

✔ Low memory

---

## Disadvantages

Can get stuck in:

### Local Maximum

```text
     /\        Highest Peak
    /  \           /\
   /    \         /  \
```

Agent stops at the smaller hill.

---

### Plateau

Flat region.

No improvement.

```text
__________
```

---

### Ridge

Requires moving sideways before improving.

```text
     /
____/
```

---

# Hill Climbing Properties

| Property | Value    |
| -------- | -------- |
| Complete | ✘        |
| Optimal  | ✘        |
| Memory   | Very Low |

---

# 4. Simulated Annealing ⭐⭐⭐⭐⭐

Hill Climbing gets stuck.

Simulated Annealing solves this by sometimes accepting **worse** moves.

Inspired by metallurgy.

---

## Idea

Sometimes move downhill

↓

Escape local maximum

↓

Eventually reach better solution.

---

### Temperature

High Temperature

↓

Many random moves

Low Temperature

↓

Mostly greedy moves

Eventually

Temperature

↓

0

Algorithm behaves like Hill Climbing.

---

## Advantages

✔ Escapes local maxima

✔ Better chance of global optimum

---

## Disadvantages

Slower

---

# Hill Climbing vs Simulated Annealing

| Hill Climbing      | Simulated Annealing   |
| ------------------ | --------------------- |
| Always better move | May accept worse move |
| Easily trapped     | Escapes traps         |
| Fast               | Slower                |
| Simple             | More robust           |

---

# 5. Local Beam Search ⭐⭐⭐⭐

Instead of maintaining one state,

keep **k** states.

```text
State 1

State 2

State 3

↓

Choose Best Successors
```

The search benefits from multiple candidates.

---

## Advantages

* Better exploration
* Less chance of poor local optima

---

# 6. Genetic Algorithm ⭐⭐⭐⭐

Inspired by biological evolution.

Basic steps:

1. Create population
2. Evaluate fitness
3. Select parents
4. Crossover
5. Mutation
6. New generation

```text
Population
      ↓
Selection
      ↓
Crossover
      ↓
Mutation
      ↓
New Population
```

---

## Important Terms

### Population

Set of candidate solutions.

---

### Fitness Function

Measures quality.

Higher fitness

↓

Better solution.

---

### Crossover

Combine two parents.

---

### Mutation

Randomly modify a solution.

Helps maintain diversity.

---

# Applications

* Timetable generation
* Route optimization
* Scheduling
* Machine Learning parameter tuning
* Robotics

---

# Comparison

| Algorithm           | Memory | Escapes Local Maxima | Complete | Optimal     |
| ------------------- | ------ | -------------------- | -------- | ----------- |
| Hill Climbing       | Low    | ✘                    | ✘        | ✘           |
| Simulated Annealing | Low    | ✔                    | ✘        | Sometimes   |
| Local Beam          | Medium | Better               | ✘        | ✘           |
| Genetic Algorithm   | Medium | ✔                    | ✘        | Approximate |

---

# Exam MCQs

Know these answers:

* Hill Climbing always chooses → **Best neighbouring state**
* Hill Climbing can fail because of → **Local maxima, plateaus, ridges**
* Simulated Annealing accepts → **Occasionally worse states**
* Local Beam Search maintains → **Multiple states simultaneously**
* Genetic Algorithm is inspired by → **Natural evolution**
* Fitness Function measures → **Quality of a solution**
* Mutation helps → **Maintain diversity and avoid premature convergence**

---

# One-Page Revision

```text
Local Search
============
Current State Only

Hill Climbing
=============
Best Neighbour

Problems
========
Local Maximum
Plateau
Ridge

Simulated Annealing
===================
Accept Worse Moves
Temperature ↓

Local Beam
==========
k States

Genetic Algorithm
=================
Population
Selection
Crossover
Mutation
Fitness
```

# 7. Online Search ⭐⭐⭐

### What is it?

In Chapter 3, the agent **knows the environment** before starting.

In **Online Search**, the agent:

* Does **not know** the environment completely.
* Learns while exploring.
* Must make decisions without a complete map.

### Example

A robot exploring a new building.

```text
Unknown Building

↓

Move

↓

Observe

↓

Learn

↓

Move Again
```

### Applications

* Mars Rover
* Exploration robots
* Rescue robots
* Unknown game maps

---

# 8. Online DFS Agent ⭐⭐

This is simply a DFS-style algorithm adapted for unknown environments.

The agent:

* Explores
* Remembers visited states
* Backtracks when necessary

Unlike ordinary DFS:

* The graph is discovered while moving.

---

# 9. LRTA* (Learning Real-Time A*) ⭐⭐

A variation of A* for real-time problems.

Idea:

Instead of computing the entire solution first,

the agent:

1. Looks locally.
2. Chooses the best move.
3. Updates its heuristic.
4. Continues moving.

### Advantages

* Real-time decisions
* Limited memory
* Learns better heuristics

Typical applications:

* Video games
* Robot navigation
* Real-time AI

---

# 10. Offline vs Online Search ⭐⭐⭐

| Offline Search    | Online Search              |
| ----------------- | -------------------------- |
| Knows environment | Environment unknown        |
| Plans first       | Learns while moving        |
| Complete map      | Discovers map              |
| Example: GPS      | Example: Exploration robot |

This comparison is a common conceptual question.

---

# 11. Local Search vs Graph Search ⭐⭐⭐⭐⭐

| Graph Search       | Local Search           |
| ------------------ | ---------------------- |
| Finds path         | Finds solution         |
| Builds search tree | Current state only     |
| High memory        | Very low memory        |
| Uses frontier      | No frontier            |
| Example: BFS       | Example: Hill Climbing |

---

# 12. When Should Each Algorithm Be Used?

| Problem             | Algorithm           |
| ------------------- | ------------------- |
| Shortest Path       | A*                  |
| Route Planning      | A*                  |
| Maze                | BFS / DFS           |
| Scheduling          | Hill Climbing       |
| Timetabling         | Genetic Algorithm   |
| Optimization        | Simulated Annealing |
| Unknown Environment | Online Search       |

---
