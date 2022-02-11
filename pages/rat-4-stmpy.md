## Question 1

:rat:What should happen if another system component wants to trigger a transition of a state machine?

1. It adds a transition into the transition table.
2. It sends a message to the driver of the state machine which then forwards it to the state machine.
3. It directly triggers the transition of the state machine by calling the transition method.
4. It adds an event into the transition table.

## Question 2

:rat:How are decisions in transitions implemented in STMPY?

1. With a switch statement.
2. With a compound transitions pointing to a Python function.
3. With choice states and guards.
4. With a decision table that includes choice pseudostates.

## Question 3

:rat:Which relationship do the classes Machine and Driver have?

1. One machine can have many parallel drivers.
2. One machine object can run many driver objects.
3. One driver object can run many machine objects.
4. One driver object is associated with one machine object.

## Question 4

:rat:How do we get the code for the state machines in STMPY?

1. Code is generated automatically from the diagrams.
2. Parts of the code are written manually, parts are generated.
3. Models are interpreted, so that there is no need for code.
4. Parts of the code are written manually, parts are provided by a library.

## Question 5

:rat:Which of the code listings is correct to define a transition?

1. Listing 3 is correct.
2. Listing 2 is correct.
3. Listing 4 is correct.
4. Listing 1 is correct.

---
type: figure
source: figures/rats/stmpy-transitions.jpg
caption: "Different listings of transition definitions. Only one is correct."
---

## Question 6

:rat:Look at the following code. Why is nothing happening when you execute it?

1. There is no initial transition.
2. There is no initial state.
3. The driver is not started.
4. The machine is not started.

---
type: figure
source: figures/rats/stmpy-starting.jpg
caption: "Code listing with an error."
---

## Question 7

:rat:A user presses a button, and this should trigger a transition. Which is the best solution?

1. The press of the button sends a message into the state machine via the driver.
2. The press of the button directly triggers a transition function.
3. The state machine continuously checks whether the button has been pressed.
4. The driver has built-in support for user interfaces.

## Question 8

:rat:The preparation material named the term "traceability". What did it mean in this context?

1. How diagram and code belong together.
2. How behavior can be presented as traces.
3. That state machines execute traces of behavior.
4. The traces that the sequences of states leave behind.

## Question 9

:rat:How are while-loops used in STMPY?

1. All drivers share a single while-loop.
2. Only a driver has a while-loop, serving all its state machines.
3. Each state machine has its own while-loop.
4. STMPY is implemented *without* while-loops.

## Question 10

:rat:How do state machines break down the complexity of concurrent behavior?

1. State machines efficiently assign programming statements to while-loops.
2. State machines define events that are efficiently scheduled.
3. State machines break down concurrent behavior into short pieces of behavior (the transitions) and execute them one at a time.
4. State machines allow to run many programming threads at the same time.
