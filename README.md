# MDP REPRESENTATION

## AIM:
The aim of this experiment is to create a Markov Decision Process (MDP) representation and implement it in Python to model the decision-making process in a Elevator Control System.
### Problem Description
The elevator control system should make decisions about which action to take based on the current floor and the possible outcomes of each action. The system must handle stochastic transitions, meaning that there is a probabilistic chance that the elevator may not reach the desired floor due to mechanical issues or other uncertainties.
### State Space
state 0: Ground Floor<br>
state 1: First Floor<br>
state 2: Second Floor (reward is achieved in top floor(2nd floor))
### Sample State
state: Ground Floor -> represented numerically as 0<br>
state: First Floor -> represented numerically as 1<br>
state: second Floor -> represented numerically as 2

### Action Space
Action 0: Moves Down<br>
Action 1: Moves Up
### Sample Action

0:[(0.9,1,-1.0,False),(0.1,1,-1.0,False)]
From Ground Floor (0) Elevator moves to next Floor that is First Floor (1) with the transition probability of 0.9
And 0.1 probability to stay in the same floor(1) and both doesn't reach the goal State of Top Floor ot earns reward of -1.0.

### Reward Function

Reward: +10.0 => If the Elevator Reaches the Top Floor of the Building<br>
Reward: -1.0 => For all other Intermidiate States
### Graphical Representation
![image](https://github.com/user-attachments/assets/bfda59d6-a890-422a-8c51-0b7cca2a4471)


## PYTHON REPRESENTATION:
```
p = {
    0: {  #GROUND FLOOR
        0:[(0.9,0,-1.0,False),(0.1,1,-1.0,False)],
        1:[(0.9,1,-1.0,False),(0.1,0,-1.0,False)]
    },
    1: { #FIRST FLOOR
        0:[(0.9,0,-1.0,False),(0.1,1,-1.0,False)],
        1:[(0.9,2,+10.0,True),(0.1,1,-1.0,False)]
    },
    2: { #SECOND FLOOR
        0:[(0.9,1,-1.0,False),(0.1,2,+10.0,True)],
        1:[(0.9,2,+10.0,True),(0.1,1,-1.0,False)]
    }
}
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/9cd1892a-2870-4749-a13f-0c27c56a04c0)


## RESULT:
Thus the given real world problem is successfully represented in a MDP form.
