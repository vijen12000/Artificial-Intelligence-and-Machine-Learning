# Chapter 5 – Adversarial Search (Part 1)

## Learning Objectives

After this chapter you should be able to:

* Explain adversarial search
* Understand game trees
* Explain Minimax
* Identify MAX and MIN players
* Compute minimax values
* Understand utility functions
* Explain optimal play

---

# 1. What is Adversarial Search? ⭐⭐⭐⭐⭐

Unlike ordinary search, **adversarial search** involves an opponent trying to prevent you from reaching your goal.

Examples:

* Chess
* Tic-Tac-Toe
* Checkers
* Connect Four

---

# 2. Terminology

### Initial State

Starting board configuration.

---

### Players

Usually two players:

* **MAX** → tries to maximize the score.
* **MIN** → tries to minimize MAX's score.

---

### Actions

Legal moves available to a player.

---

### Terminal State

A game state where the game ends.

Examples:

* Win
* Lose
* Draw

---

### Utility Function ⭐⭐⭐⭐⭐

Assigns a numerical value to a terminal state.

Example:

| Result | Utility |
| ------ | ------- |
| Win    | +1      |
| Draw   | 0       |
| Lose   | -1      |

The utility function is what Minimax tries to optimize.

---

# 3. Game Tree ⭐⭐⭐⭐⭐

A game tree represents all possible moves.

```text
            MAX
          /     \
        MIN     MIN
       /  \     /  \
      3    5   2    9
```

Leaves represent terminal states with utility values.

---

# 4. Minimax Algorithm ⭐⭐⭐⭐⭐

### Idea

* MAX chooses the move with the **highest** utility.
* MIN chooses the move with the **lowest** utility.

Both players are assumed to play optimally.

---

## Algorithm

1. Expand the game tree.
2. Assign utilities to terminal nodes.
3. MIN chooses the minimum value.
4. MAX chooses the maximum value.
5. Continue until the root is evaluated.

---

### Example

```text
             MAX
           /     \
        MIN       MIN
      /   \      /   \
     3     5    2     9
```

MIN values:

* Left = min(3,5) = **3**
* Right = min(2,9) = **2**

MAX chooses:

max(3,2) = **3**

Optimal value = **3**

---

# 5. Properties of Minimax

✔ Complete (for finite game trees)

✔ Optimal (against an optimal opponent)

✘ Very expensive for large game trees

---

# 6. Time Complexity

If:

* **b** = branching factor
* **m** = maximum depth

Then:

Space complexity (depth-first implementation):

---

# 7. Minimax Example (Exam Style)

Given:

```text
              MAX
            /      \
         MIN        MIN
       /   \       /   \
      8     4     6     2
```

Step 1:

Left MIN = min(8,4) = **4**

Right MIN = min(6,2) = **2**

Step 2:

MAX = max(4,2) = **4**

**Answer: 4**

---

# 8. Frequently Asked MCQs

* The player trying to maximize the score is → **MAX**
* The opponent is → **MIN**
* Minimax is used for → **Two-player adversarial games**
* Terminal states are evaluated using → **Utility Function**
* MAX chooses → **Maximum utility**
* MIN chooses → **Minimum utility**

---

# One-Page Revision

```text
Adversarial Search
==================
Opponent Present

Players
=======
MAX
MIN

Terminal State
==============
Win
Lose
Draw

Utility
=======
Win = +1
Draw = 0
Lose = -1

Minimax
=======
MAX → Maximum
MIN → Minimum

Complexity
==========
Time = O(b^m)
Space = O(bm)
```

---

# 1. Why Alpha-Beta Pruning?

Problem:

Minimax searches **every node**.

For Chess,

```text
35 possible moves

↓

35^8 positions
```

Millions of nodes.

Too slow.

---

## Solution

Skip branches

that

**cannot affect**

the final decision.

This is called

> **Alpha-Beta Pruning**

---

# 2. Idea Behind Alpha-Beta ⭐⭐⭐⭐⭐

Suppose

```text
Root

↓

Already found value = 8
```

Another branch

cannot exceed

8.

No need

to search it.

↓

Prune.

---

# 3. Alpha (α)

Alpha

=

Best value

MAX

can guarantee.

Initially

```text
α = -∞
```

Whenever MAX finds

a better value

↓

Update α.

---

# 4. Beta (β)

Beta

=

Best value

MIN

can guarantee.

Initially

```text
β = +∞
```

Whenever MIN finds

a smaller value

↓

Update β.

---

# Memory Trick

```text
Alpha

MAX

Highest
```

```text
Beta

MIN

Lowest
```

---

# 5. Pruning Condition ⭐⭐⭐⭐⭐

Pruning occurs whenever

Meaning

MAX already has

a better option.

No need

to continue exploring.

---

# 6. Alpha-Beta Example

Consider

```text
              MAX
            /      \
         MIN        MIN
       /   \       /   \
      3     5     2     9
```

Evaluate Left

MIN

↓

min(3,5)=3

Root

```text
α=3
```

Now Right

First child

↓

2

```text
β=2
```

Now

```text
α=3

β=2
```

Since

```text
3≥2
```

Prune

9.

Need not evaluate it.

---

# 7. Important Observation

Alpha-Beta

Produces

**Exactly**

the same answer

as

Minimax.

Difference

Only

fewer nodes

are evaluated.

---

# 8. Best Case Complexity ⭐⭐⭐⭐

Minimax

Alpha-Beta

(Best Ordering)

Huge improvement.

---

# 9. Worst Case

Worst ordering

↓

No pruning.

Complexity

Same as

Minimax.

---

# 10. Move Ordering ⭐⭐⭐⭐

Better move ordering

↓

More pruning.

Poor ordering

↓

Little pruning.

---

# 11. Evaluation Function ⭐⭐⭐⭐⭐

In Chess,

complete search

is impossible.

Instead,

estimate

board quality.

This estimate

is called

> **Evaluation Function**

---

Example

```text
Material Score

King

Queen

Rook

Bishop

Knight

Pawn
```

Higher score

↓

Better board.

---

# 12. Utility Function vs Evaluation Function ⭐⭐⭐⭐⭐

| Utility Function        | Evaluation Function         |
| ----------------------- | --------------------------- |
| Used at terminal states | Used at non-terminal states |
| Exact value             | Estimated value             |
| Win = +1                | Approximation               |
| Lose = -1               | Heuristic                   |

Very common MCQ.

---

# 13. Cutoff Search ⭐⭐⭐⭐

Searching entire tree

is impossible.

Solution

Stop search

at

fixed depth.

Example

```text
Depth

0

↓

1

↓

2

↓

3

Stop
```

Use

Evaluation Function

instead.

---

# 14. Horizon Effect

Agent

cannot see

events

beyond

cutoff depth.

Leads

to poor decisions.

Example

Chess

Sacrifice Queen

Looks good

Initially

Actually loses later.

---

# 15. Quiescence Search

Solution

Continue searching

until

position becomes

stable.

Avoids

Horizon Effect.

---

# 16. Iterative Deepening ⭐⭐⭐

Search

Depth 1

↓

Depth 2

↓

Depth 3

↓

Depth 4

Keeps improving

answer.

Often used

with Alpha-Beta.

---

# 17. Transposition Table ⭐⭐

Sometimes

same board

appears

multiple times.

Store

evaluated positions.

Avoid

recomputing.

---

# 18. Comparison

| Feature            | Minimax | Alpha-Beta |
| ------------------ | ------- | ---------- |
| Finds Optimal Move | ✔       | ✔          |
| Pruning            | ✘       | ✔          |
| Fewer Nodes        | ✘       | ✔          |
| Same Result        | ✔       | ✔          |

---

# 19. Important Formulae

Minimax

Alpha-Beta

Best

Pruning

---

# 20. Frequently Asked MCQs

### Alpha represents

✅ Best value for MAX

---

### Beta represents

✅ Best value for MIN

---

### Pruning occurs when

✅ α ≥ β

---

### Alpha-Beta changes

Final Answer?

❌ No

---

### Evaluation Function

Used for

✅ Non-terminal nodes

---

### Utility Function

Used for

✅ Terminal nodes

---

### Best case complexity

Alpha-Beta

✅ O(b^(m/2))

---

### Worst case

Alpha-Beta

✅ Same as Minimax

---

# Common Viva Questions

### Why is Alpha-Beta better?

Because it eliminates branches that cannot influence the final decision while producing the same optimal move as Minimax.

---

### Why is Alpha-Beta important?

It significantly reduces the number of evaluated nodes, allowing deeper searches within the same amount of time.

---

### Why use an Evaluation Function?

Because searching all the way to terminal states is usually infeasible in large games such as chess.

---

# One-Page Revision Sheet

```text
Game Playing
============
MAX
MIN

Utility
=======
Win = +1
Draw = 0
Lose = -1

Minimax
=======
MAX → Maximum

MIN → Minimum

Alpha
=====
Best for MAX

Beta
====
Best for MIN

Pruning
========
α ≥ β

Evaluation Function
===================
Estimate Position

Utility Function
================
Terminal Position

Alpha-Beta
===========
Same Answer

Less Search

Best Time
=========
O(b^(m/2))
```

---
