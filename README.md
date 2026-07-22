# MDP REPRESENTATION

## AIM:
To model the Student Exam Preparation process using a Markov Decision Process (MDP).

## PROBLEM STATEMENT:

### Problem Description
A student prepares for an examination by choosing different actions such as Study, Revise, or Take Break. The student's preparation level changes depending on the action taken. Studying improves preparation, revising helps maintain knowledge, and taking a break may reduce preparation. Each action provides a reward based on its effect.

### State Space
The states represent the student's preparation level.

State 1 (S1): Poor Preparation

State 2 (S2): Average Preparation

State 3 (S3): Well Prepared

### Sample State
```
State 2 (Average Preparation)
The student has an average level of preparation for the examination.
```

### Action Space
There are three possible actions.

0 - STUDY

1 - REVISE

2 - TAKE_BREAK

### Sample Action
```
STUDY – Improves the student's preparation.
REVISE – Helps maintain the current preparation level.
TAKE_BREAK – May reduce the student's preparation level.
```

### Reward Function
STUDY and improve preparation : +10

REVISE and remain well prepared : +5

TAKE_BREAK : −2

### Graphical Representation
<img width="1602" height="982" alt="ChatGPT Image Jul 22, 2026, 09_57_04 AM" src="https://github.com/user-attachments/assets/f5714856-47e9-4f18-9a83-d5fe6f2b66d7" />

## PYTHON REPRESENTATION:
```
P = {

    1: {                                 # State 1 : Poor Preparation
        0: [                             # Action 0 : STUDY
            (0.8, 2, 10, False),
            (0.2, 1, -2, False)
        ]
    },

    2: {                                 # State 2 : Average Preparation
        0: [                             # Action 0 : STUDY
            (0.7, 3, 10, False),
            (0.3, 2, 5, False)
        ],

        2: [                             # Action 2 : TAKE_BREAK
            (0.3, 1, -2, False),
            (0.7, 2, 5, False)
        ]
    },

    3: {                                 # State 3 : Well Prepared
        1: [                             # Action 1 : REVISE
            (0.6, 3, 5, True),
            (0.4, 2, -2, False)
        ]
    }
}
print(P)
```
## OUTPUT:
<img width="511" height="95" alt="image" src="https://github.com/user-attachments/assets/0df4c2ed-6d96-411b-838c-16da1c1f071b" />

## RESULT:
Thus, the Student Exam Preparation problem is successfully represented using a Markov Decision Process (MDP) by defining the states, actions, transition probabilities, rewards, and state transitions. This representation helps in determining the optimal sequence of actions that maximizes the student's preparation and overall reward.
