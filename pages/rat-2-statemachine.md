## Question 1

:rat:What is the difference between normal states and pseudostates, like the initial state and choice states?

1. Pseudo states are mutual exclusive to each other.
2. Pseudo states are transient, i.e., the state machine does not wait in them.
3. Pseudo states are only seldom used.
4. Pseudo states are a shorthand notation for a structure of simple states.

## Question 2

:rat:Which of the statements is true about internal transitions?

1. An internal transition executes internal behavior, not visible outside the state machine.
2. An internal transition starts and ends in the same state.
3. An internal transition is drawn with the same notation as a transition that connects two states.
4. An internal transition invokes entry and exit actions.

## Question 3

:rat:The state machine below contains some actions. Only one of the four sequences of actions and triggering events is actually possible. Which?

1. a, c
2. a, d, op4
3. a, op1, c, d, op4
4. a, op1, c, op3, d, op2, op4

---
type: figure
source: figures/rats/stm-1.png
---

## Question 4

:rat:Which of the elements in a label for a transition (that means, triggering event, guard, behavior) are optional?

1. all (triggering event, guard, behavior) are optional
2. the triggering event is optional
3. only guards and behavior are optional
4. when a guard is specified, there must also be a trigger

## Question 5

:rat:Look at the picture below.

1. two!
2. three!
3. four!
4. one!


---
type: figure
source: figures/rats/stm-2.png
---

## Question 6

:rat:Which of the following statements is true?

1. Entry and exit actions are forms of internal transitions.
2. A state can declare any number of entry or exit actions.
3. Transition can take a long time.
4. The choice pseudostate has exactly one outgoing and any number of incoming transitions.

## Question 7

:rat:Assume the state machine below is in state `A`, and x has the value 5. What happens when the event `e3` happens?

1. x keeps its value of 5.
2. The entry action resets x to 2.
3. Nothing happens.
4. The exit action increases x to 6.

---
type: figure
source: figures/rats/stm-4.png
---

## Question 8

:rat:What about self-transitions?

1. A self-transition can have different source and target states.
2. A self-transition always triggers an entry action.
3. A self transition is triggered by the termination of an action.
4. A self-transition is drawn with the same notation as a transition that connects two different states.

## Question 9

:rat:What kind of behavior do state machines present?

1. State machines specify complete behavior, i.e., all possible sequences of events.
2. State machines only show selected traces of events.
3. State machines only specify sequential behavior without choices.
4. State machines specify concurrent partial behavior.

## Question 10

:rat:Which statement is true about choice states?

1. Choices should have an outgoing else branch.
2. Choices only model different traces, not decisions like if-statements do.
3. Choices states must have incoming transitions with else branches.
4. Choices can originate from internal transitions.
