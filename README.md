# Representation-of-a-Real-World-Problem-as-a-Markov-Decision-Process


## Aim

To model a Personalized Adaptive Tutoring System as a Markov Decision Process by formally defining its state space, action space, transition dynamics, reward function, and Python dictionary representation.

---

## Problem Statement

### Problem Description
Online learning platforms often deliver static content that fails to adjust to individual student pace, leading to boredom or frustation and dropout.
We design an adaptive AI tutoring agent that sequentially selects practice problem topics and difficulty levels for a student learning a subject by observing their proficiency levels and recent correctness. 


---

## MDP Components

A Markov Decision Process is represented as:

$$
MDP = (S, A, P, R, \gamma)
$$

Where:

| Symbol | Meaning |
|---|---|
| $S$ | Set of states |
| $A$ | Set of actions |
| $P$ | Transition probability function $P(s' \mid s, a)$ |
| $R$ | Reward function $R(s, a, s')$ |
| $\gamma$ | Discount factor ($\gamma \in [0, 1]$) |

---

## State Space

The state space represents the student's estimated mastery level (Low, Medium, High) combined with their outcome on the previous exercise (Incorrect, Correct).

```
S = {
    (Low, Incorrect),
    (Low, Correct),
    (Medium, Incorrect),
    (Medium, Correct),
    (High, Incorrect),
    (High, Correct)
}
```

## Sample State

s = (Medium, Correct) — The student currently possesses Medium topic mastery and answered the most recent problem correctly.


## Action Space

The action space consists of the teaching decision selected by the AI tutor for the next exercise:

```
A = {
    Remediate_Easy,    # Provide an easy problem / review basic concepts
    Practice_Medium,   # Provide a standard, medium-difficulty problem
    Challenge_Hard     # Provide a challenging, advanced problem
}
```

## Sample Action

a = Practice_Medium — The AI tutor chooses to give the student a medium-difficulty problem.


## Transition Probability

The transition probability explains how the student's state evolves from $s$ to $s'$ after receiving an exercise type $a$:
$$P(s' \mid s, a)$$

If a student in (Low, Correct) is given Practice_Medium, there is a high probability ($P = 0.70$) they transition to (Medium, Correct) as their skill increases, and a smaller probability ($P = 0.30$) they fail and transition to (Medium, Incorrect).

If given an exercise that is too difficult (Challenge_Hard in a Low state), the probability of failure and falling back to (Low, Incorrect) is high ($P = 0.85$).Reward Function


## Reward Function

The reward function $R(s, a, s')$ gives positive feedback when student mastery increases and penalizes decisions that cause frustration (overwhelming the student) or boredom (under-challenging the student):

$+10$: Transitioning to a higher mastery state (e.g., Medium $\rightarrow$ High)

$+2$: Maintaining practice at the appropriate skill level (e.g., Medium state given Practice_Medium)

$-5$: Giving an overly hard problem to a struggling student, causing frustration (e.g., Low state given Challenge_Hard)

$-3$: Giving an overly easy problem to an advanced student, causing boredom (e.g., High state given Remediate_Easy).

## Graphical Representation

Draw the MDP graph.

The graph should include:

1. States as nodes.
2. Actions as arrows.
3. Rewards on transitions.
4. Transition probabilities if applicable.

<img width="1214" height="1295" alt="image" src="https://github.com/user-attachments/assets/747aa59d-37aa-49a0-81e0-f9e54711b3c0" />

---

## Python Representation

Write your code here.

Use Python dictionaries to represent the MDP.


```python
# MDP Representation using Python
# print("Name: THARUN SRIDHAR")
# print("Register Number: 212223230230")

```
---
## Output

Write your Python output here.


---

## Result

Write your result here.



---

