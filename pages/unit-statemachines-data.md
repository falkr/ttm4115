# State Machines: Data vs. States


As you have seen, state machines can have choice states so that transitions can contain decisions, similar to if-statements in programming languages.
In principle, you could design a state machine that only has a single state, yet handles many incoming messages and timers. This state machine could store all information in its variables, and use lots of guards on the transitions. It would obey all rules of a consistent state machine we have listed so far.

---
type: figure
source: figures/statemachines/stateless-machine.png
caption: "A state machine with only a single state. Possible, syntactically correct, and also completely useless. Not recommended."
---

Above we see a machine that is syntactically correct. It consists of only a single state `s_1`, and declares outgoing triggers `A`, `B`, `C`. For each of these triggers it defines compound transitions that contain a choice state with an outgoing guard. These guards determine what the state machine is doing, like execurting actions attached to the branches of the transitions (not shown here). So this is a valid state machine, and totally possible to produce. But is it a good idea?


In most cases, this is a **bad design** for a state machine. It does not use the concept of control states, and will be hard to understand. 
States are really hidden in the data of the machine.
Instead, the states should follow what is happening in the real world or follow the state of an interaction explicitly by using its control states. 

Of course, variables should be used to store values, and in some cases, these values have an influence on the guards of choice states. But variables should not be stored to remember the state of an interactions, like a variable that would store if you have previously received a specific message. Equally, you should not access an API to check if a timer is still active or allready expired. This you should express with states and dedicated transitions.

### Example

Similar to the strategy with the decisions above, we could realize the state machine shown below. It should monitor the arrival of a message `A`. If it arrives in time (i.e., before timer `t` expires), we want to go into state `in_time`, otherwise we go into state `too_late`. The solution below uses a decision once the message `A` arrives and checks iof the timer alreay expired, to then decide where to go.

---
type: figure
source: figures/statemachines/stateless-timer-1.svg
caption: "Using a choice state with a decision to query the state of the timer. Not recommended."
---

Although the solution above is syntactically okay, it is not a good design. Obviously, the fact if the message arrived in time or too late has something to do with the flow of the conversation between this state machine and wherever `A` comes from. The fact that the timer `t` expired is n the design above not visible form the control state. When we debug the state machine, we don't see that it is in a differnet state, and we also have to look at the timer queue to understand the current state of the system. 

The solution below is much better. Here we use states the way they are useful. When the timer expires, the state machine switches into state `still_waiting`, which already signifies that `A` is late. In this design, the control flow follows the flow of the conversation, and encodes that the timer expires. 

---
type: figure
source: figures/statemachines/stateless-timer-2.svg
caption: "Recommended, state-based design realizing the same functionality."
---