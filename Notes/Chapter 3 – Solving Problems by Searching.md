### Part 1 – Problem Formulation & Uninformed Search

---

# Learning Objectives

After studying this chapter, you should be able to:

* Define a search problem
* Explain problem formulation
* Understand state space search
* Compare uninformed search algorithms
* Solve BFS/DFS/UCS questions
* Analyze time and space complexity
* Determine completeness and optimality

---

# 1. What is Search?

Search is the process of finding a sequence of actions that transforms an **initial state** into a **goal state**. 

```text
Initial State
      ↓
Actions
      ↓
Intermediate States
      ↓
Goal State
```

---

# 2. Components of a Search Problem ⭐⭐⭐⭐⭐

Every search problem consists of:

### 1. Initial State

Starting point.

Example:

Arad

---

### 2. Actions

Possible moves.

Example

```text
Move Left

Move Right

Move Up

Move Down
```

---

### 3. Transition Model (Result Function)

Defines

```text
State + Action
        ↓
Next State
```

Example

```text
Arad

Right

↓

Sibiu
```

---

### 4. Goal Test

Checks

```text
Have we reached the goal?
```

Returns

True

or

False

---

### 5. Path Cost

Total cost from start to goal.

```text
Total Cost

=

Sum of Edge Costs
```

---

# 3. State Space ⭐⭐⭐⭐⭐

State Space

=

All possible states reachable from the initial state.

Example

8 Puzzle

Every board configuration

is a state.

---

# 4. Search Tree

A Search Tree is generated during search.

```text
         Start
        /  |  \
       A   B   C
      / \      |
     D   E     F
```

Don't confuse it with the **state-space graph**.

A state may appear multiple times in a search tree.

---

# 5. Tree Search vs Graph Search ⭐⭐⭐⭐⭐

## Tree Search

* No visited list
* May revisit states
* More memory efficient
* Can loop forever

---

## Graph Search

Uses

```text
Explored Set
```

Advantages

* Avoids repeated states
* Prevents cycles
* More efficient

---

# 6. Uninformed Search

Also called

Blind Search

No heuristic.

Uses only

* Initial State
* Operators
* Goal Test
* Path Cost

Algorithms

* BFS
* DFS
* Uniform Cost Search
* Depth Limited Search
* Iterative Deepening Search
* Bidirectional Search

---

# 7. Breadth First Search (BFS) ⭐⭐⭐⭐⭐

Idea

Explore

Level by Level

Uses

FIFO Queue

```text
Queue

Front

A

B

C

Rear
```

---

### Properties

Complete

✔ Yes

Optimal

✔ Yes

(when all edge costs are equal)

---

Time

```text
O(b^(d+1))
```

Space

```text
O(b^(d+1))
```

Very High Memory

---

Advantages

✔ Finds shortest path

✔ Complete

---

Disadvantages

Large memory requirement

---

Exam Favourite

Uses

FIFO Queue

---

# 8. Depth First Search (DFS) ⭐⭐⭐⭐⭐

Idea

Go as deep as possible.

Uses

Stack

(or recursion)

```text
Stack

Top

C

B

A
```

---

Properties

Complete

✘ No

(in infinite trees)

Optimal

✘ No

---

Time

```text
O(b^m)
```

Space

```text
O(bm)
```

Memory Efficient

---

Advantages

Low memory

---

Disadvantages

Can get stuck in infinite paths

---

# 9. Uniform Cost Search (UCS) ⭐⭐⭐⭐⭐

Idea

Expand node with

Lowest Path Cost

Uses

Priority Queue

Ordered by

```text
g(n)
```

---

Example

```text
A

↓

Cost 2

↓

B

↓

Cost 5

↓

Goal
```

Always expands the smallest cumulative cost first.

---

Properties

Complete

✔ Yes

Optimal

✔ Yes

(if costs are positive)

---

Complexity

```text
O(b^(1+C*/ε))
```

Where

* **b** = Branching factor
* **C*** = Optimal solution cost
* **ε** = Minimum positive edge cost

This exact formula appeared in one of your PT questions.

---

# 10. Depth Limited Search (DLS)

DFS

*

Depth Limit

Stops after

Depth = L

---

Advantages

Prevents infinite loops

---

Disadvantages

May miss solution

if

Goal

>

Limit

---

# 11. Iterative Deepening Search (IDS) ⭐⭐⭐⭐⭐

Idea

Run DLS repeatedly

```text
Depth 0

↓

Depth 1

↓

Depth 2

↓

Depth 3
```

---

Properties

Complete

✔ Yes

Optimal

✔ Yes

(equal costs)

---

Memory

Same as DFS

```text
O(bd)
```

---

Time

Same as BFS

Approximately

```text
O(b^d)
```

---

Important Concept

Why is IDS efficient despite repeated node generation?

Because **most nodes are at the deepest level**, so regenerating the upper levels adds relatively little overhead. This was directly tested in your PT. 

---

# 12. Bidirectional Search ⭐⭐⭐⭐

Idea

Search

From Start

AND

From Goal

Until they meet.

```text
Start

↓

↓

Meeting Point

↑

↑

Goal
```

---

Usually implemented using

Two BFS

---

Advantages

Reduces search depth

From

d

to

d/2

---

# 13. Comparison Table ⭐⭐⭐⭐⭐

| Algorithm     | Data Structure | Complete | Optimal |
| ------------- | -------------- | -------- | ------- |
| BFS           | Queue          | ✔        | ✔       |
| DFS           | Stack          | ✘        | ✘       |
| UCS           | Priority Queue | ✔        | ✔       |
| DLS           | Stack          | Depends  | ✘       |
| IDS           | Stack          | ✔        | ✔       |
| Bidirectional | Two Queues     | ✔        | ✔       |

---

# 14. Important Formulae ⭐⭐⭐⭐⭐

BFS

```text
Time = O(b^(d+1))

Space = O(b^(d+1))
```

DFS

```text
Time = O(b^m)

Space = O(bm)
```

UCS

```text
Time = O(b^(1+C*/ε))
```

IDS

```text
Time = O(b^d)

Space = O(bd)
```
* Explain heuristic search
* Define heuristic function
* Differentiate Greedy Search and A*
* Explain admissible and consistent heuristics
* Solve A* problems
* Explain RBFS
* Compare all search algorithms

---

# 1. What is Informed Search? ⭐⭐⭐⭐⭐

Unlike uninformed search, informed search uses **additional knowledge** about the problem.

This knowledge is called a **heuristic**.

```text
Current State
      ↓
Heuristic Estimate
      ↓
Choose Better Node
```

---

# 2. Heuristic Function h(n) ⭐⭐⭐⭐⭐

A heuristic function estimates:

> **The remaining cost from the current node to the goal.**

Notation

```text
h(n)
```

Where

* n = current node
* h(n) = estimated cost to goal

---

## Example

Suppose

```text
Delhi -------- Mumbai

Actual Distance

1400 km
```

If heuristic estimates

```text
1300 km
```

then

```text
h(n)=1300
```

---

# Important Properties

### At Goal

```text
h(goal)=0
```

This appeared in one of your PT questions.

---

### Never Negative

Normally

```text
h(n) ≥ 0
```

---

# 3. Evaluation Function ⭐⭐⭐⭐⭐

Different search algorithms evaluate nodes differently.

| Algorithm | Evaluation |
| --------- | ---------- |
| BFS       | Depth      |
| DFS       | Depth      |
| UCS       | g(n)       |
| Greedy    | h(n)       |
| A*        | g(n)+h(n)  |

---

# 4. Path Cost g(n)

```text
g(n)
```

Actual cost

From

Start

↓

Current Node

---

Example

```text
Start

↓

5

↓

Current Node
```

Then

```text
g(n)=5
```

---

# 5. Greedy Best-First Search ⭐⭐⭐⭐⭐

Idea

Expand node with

Smallest

```text
h(n)
```

Evaluation Function

```text
f(n)=h(n)
```

---

Example

```text
City A

↓

Goal

Estimated Distance

25 km
```

Choose node with smallest estimated distance.

---

Advantages

✔ Fast

✔ Often finds solution quickly

---

Disadvantages

✘ Not optimal

✘ May get trapped

---

Important MCQ

Greedy Best-First Search focuses on

✅ **Minimizing estimated future cost h(n)**

This was one of your PT questions.

---

# 6. A* Search ⭐⭐⭐⭐⭐

The most important search algorithm.

A* combines:

Actual cost

*

Estimated cost

---

Evaluation Function

Where

* g(n) = actual path cost
* h(n) = heuristic estimate

---

## Interpretation

```text
Past Cost

+

Future Estimate

=

Total Estimated Cost
```

---

## Example

```text
Start

↓

Current

↓

Goal

g(n)=8

h(n)=4
```

Then

```text
f(n)=12
```

---

# 7. Why is A* Better?

Greedy

Only looks ahead.

UCS

Only looks behind.

A*

Looks at

Both.

---

# 8. A* Properties ⭐⭐⭐⭐⭐

Complete

✔ Yes

Optimal

✔ Yes

If heuristic is admissible.

---

Important PT Question

A*

Uses

```text
g(n)+h(n)
```

Answer

✔ Correct

---

# 9. When Does A* Become UCS?

Very Important

If

Then

```text
f(n)=g(n)
```

Therefore

A*

=

Uniform Cost Search

This appeared directly in your PT.

---

# 10. Admissible Heuristic ⭐⭐⭐⭐⭐

Definition

A heuristic is admissible if

It

**never overestimates**

the true cost.

---

Mathematically

Where

* h(n) = heuristic
* h*(n) = true cost

---

Memory

Admissible

↓

Optimistic

---

PT Question

Which property must an admissible heuristic possess?

Answer

✔ Never overestimates true goal cost.

---

# 11. Consistent Heuristic ⭐⭐⭐⭐⭐

Also called

Monotone Heuristic

Condition

Meaning

Estimated cost

cannot decrease too quickly.

---

Very Important Property

Along a path

```text
f(n)

never decreases
```

This was one of your PT questions.

---

# Admissible vs Consistent

| Admissible            | Consistent                     |
| --------------------- | ------------------------------ |
| Never overestimates   | Satisfies triangle inequality  |
| Guarantees optimality | Guarantees non-decreasing f(n) |
| Simpler               | Stronger property              |

---

# 12. Straight-Line Distance Heuristic ⭐⭐⭐⭐

Common heuristic

Road Maps

```text
Air Distance
```

Example

Delhi

↓

Mumbai

Straight Line

---

Advantages

Easy

Admissible

---

Limitation

Roads

are

not straight.

Therefore

It estimates,

not exact path cost.

This was asked in your PT.

---

# 13. 8-Puzzle Heuristics ⭐⭐⭐⭐⭐

Most common heuristics

---

## A. Misplaced Tiles

Count

Wrong tiles.

Example

```text
5 tiles

Wrong

↓

h=5
```

---

## B. Manhattan Distance

Add

Horizontal Distance

*

Vertical Distance

for every tile.

---

Which is better?

✔ Manhattan Distance

Usually more informed.

---

Interesting PT Question

Misplaced Tiles becomes exact if

✔ Tile can move directly to its goal.

---

# 14. Recursive Best-First Search (RBFS) ⭐⭐⭐⭐⭐

Problem

A*

Consumes

Too much memory.

---

Solution

RBFS

Stores

Only

Current Path

Memory

Linear

Like DFS

---

Characteristics

✔ Linear Space

✔ Uses heuristic

✔ Re-expands nodes

---

PT Question

How does RBFS maintain linear memory?

✔ It abandons and later regenerates subtrees instead of storing the entire frontier.

---

# 15. Comparison of Heuristic Algorithms ⭐⭐⭐⭐⭐

| Algorithm | Evaluation | Optimal                       |
| --------- | ---------- | ----------------------------- |
| Greedy    | h(n)       | ✘                             |
| A*        | g+h        | ✔                             |
| RBFS      | g+h        | ✔ (with admissible heuristic) |

---

# 16. Complete Search Comparison ⭐⭐⭐⭐⭐

| Algorithm | Structure      | Uses Heuristic | Complete | Optimal |
| --------- | -------------- | -------------- | -------- | ------- |
| BFS       | Queue          | ✘              | ✔        | ✔       |
| DFS       | Stack          | ✘              | ✘        | ✘       |
| UCS       | Priority Queue | ✘              | ✔        | ✔       |
| Greedy    | Priority Queue | ✔              | ✘        | ✘       |
| A*        | Priority Queue | ✔              | ✔        | ✔       |
| IDS       | Stack          | ✘              | ✔        | ✔       |
| RBFS      | Recursion      | ✔              | ✔        | ✔       |

---

# 17. Frequently Asked MCQs

Know these answers:

✔ Greedy uses → **h(n)**

✔ UCS uses → **g(n)**

✔ A* uses → **g(n)+h(n)**

✔ At goal → **h(goal)=0**

✔ Admissible → **Never overestimates**

✔ Consistent → **f(n) never decreases along a path**

✔ Straight-line distance → **Admissible heuristic for route finding**

✔ RBFS → **Linear memory**

✔ A* becomes UCS when → **h(n)=0**

---

# 18. Common Numerical Questions

You may be asked to compute:

* g(n)
* h(n)
* f(n)

Example:

```text
g(n)=8

h(n)=5
```

Then

```text
f(n)=13
```

Always remember:

> **A*** expands the node with the **smallest f(n)**.

---

# 19. One-Page Revision Sheet

```text
Informed Search
===============
Uses Heuristic

g(n)
=====
Actual Cost

h(n)
=====
Estimated Cost

A*
==
f=g+h

Greedy
=======
f=h

UCS
====
f=g

Admissible
==========
Never Overestimates

Consistent
==========
f never decreases

8 Puzzle
========
Misplaced Tiles
Manhattan Distance

RBFS
====
Linear Memory

A*=UCS
=======
When h(n)=0
```
