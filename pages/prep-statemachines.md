# State Machines

In the previous units, we learned how to capture and understand our user's requirements for a system, and structure what the system should provide to its users in the form of use cases. We have also learned how to use deployment diagrams to reveal already some details about the structure of the system. This week, we start with the specification of **how the system actually works.** This will be more technical and on a more detailed level as before. 


## Hello, State Machines!

In the following, we are going to learn the concept of state machines. Besides sequence diagrams and activities, state machines are one of the fundamental ways to describe behavior. They are used to specify communication protocols, logic in embedded systems, and in general behavior where events need to be coordinated in a complex way. Here is an intuitive example of a sketch for a state machine that illustrates in a compact way how a traffic light works:

---
type: figure
source: figures/statemachines/state-machines-traffic-light.jpg
caption: "A state machine describing the sequence of phases in a traffic light."
---

Another example is the specification of the TCP protocol, also using a state machine:

---
type: figure
source: figures/statemachines/state-machines-tcp.gif
caption: "The TCP protocol uses state machines to describe parts of its behavior."
---


A bit of a problem with state machines is that developers often only understand they they should have used a state machine for a problem *after* it is too late, and they already spent much effort on trying to solve a task in other ways. Have a look at this blog post from developer Alan Skorkin, [Why Developers Never Use State Machines][skorkin]. 

[skorkin]: https://www.skorks.com/2011/09/why-developers-never-use-state-machines/

Another example is the construction of the kernel for GNU. There you have a situation where the behavior quickly became very complex. Have a look at the interview with Richard Stallman:  

---
type: youtube
video: jw8K460vx1c
start: 1525
caption: "Interview with Richard Stallman, from  0:25:25 until 0:26:30, from the movie _Revolution OS_. You may watch the entire movie later." 
---

When he says _"It took us years to get the thing to work."_, you can imagine how frustrating it can be to handle concurrent behavior and not getting it under control. There are problems that look simple but that can quickly grow very complex, and state machines offer a way to handle complexity that plays out very beneficial in such situations. With state machines, you can structure complex behavior such that:

- It is easy to debug and understand precisely what happened.
- Only one thing happens at a time.
- You have detailed control over concurrency.


Given the complexity they handle, state machines are relatively easy to understand.
There is also more than one way to approach an understanding of state machines:

- State machines as a mathematical concept
- State machines as a diagram
- State machines as implementation pattern in code
- State machines as abstract machines that execute some behavior

This week, we will introduce state machines by their diagrams and explain their meaning by describing an abstract machine. Next week, we will introduce how you can implement state machines in Python. So this gives you three different entry points into the concept of state machines.


# Example: Traffic Light


Let's assume we need to describe how a traffic light works. One idea is to just take pictures of a traffic light, like this:


---
type: figure
source: figures/statemachines/traffic-light-1.jpg
---

That already helps --- the photos describe the phases in which we can observe the traffic light. Whenever we look at the traffic light, we it is in one of the phases described by the photos. For easier reference we have even given these photos some labels, intuitively _red_, _red-yellow_, _green_ and _yellow_. (The _red-yellow_ is common in many, but not all countries.)


The photos already help explaining the traffic light. But imagine you want to explain on paper on which sequence a traffic light switches its lights. One way is text, but a simpler way is to add arrows between the photos, like this:

---
type: figure
source: figures/statemachines/traffic-light-2.jpg
---

Of course, the picture above is a simplification. Some trafic lights are switched off at night and just blink yellow. The same happens as a default state in case there is an error in the controller. We can show this blinking with the two additional photos _blink-off_ and _blink-on_. The two arrows between them show how the blinking is created by two phases, one with the yellow light on and one with all lights off. We also show that blinking can be started from any of the other phases, because an error can always happen, and the lights may be switched off at any time. When we get out of the blinking sequence, we go towards the phase _red_ for safety. 


---
type: figure
source: figures/statemachines/traffic-light-3.jpg
---

That's a pretty complete and detailed description of a traffic light. As one last thing we add an arrow to mark in which phase a traffic light starts once it is switched on for the first time. For safety, we put it into _red_ first.


# State Machine Diagrams


For the traffic light above we described actually a state machine. Since taking photos of real objects is cumbersome, and we also want to describe abstract things we cannot take a photo off, we replace the photos above with a more convenient symbol, a rectangle with rounded corners. These are the states in which the traffic light can be. A state machine for the traffic light looks hence like this:

---
type: figure
source: figures/statemachines/traffic-light-4.svg
---

Noice the detailed elements in this diagram:

- The frame has a five-cornered compartment at the top, showing the name of the state machine, prefixed with the keyword `stm`.
- The states are shown as rounded rectangles. The state names are shown in bold text. As a naming convention, we only use lowercase letters, numbers, and underscores for state machine names, similar to rules for variable names in programming languages.
- The start of the state machine is shown by a compact black dot. This is also a state, called the _initial state_. Once the state machine is activated, it leaves this initial state.


## States

Pay attention to the state symbol. It's a rectangle with some rounded corners, nothing else!

---
type: figure
source: figures/statemachines/state-shapes.svg
---

State symbols with the same name refer to the same state. This means, we can use a copy of the state symbol to make our layout easier, without changing what we actually mean by the diagram. For instance, we can remove the long arrow from state `yellow` to state `red` just by having another copy of the symbol for state `red`:

---
type: figure
source: figures/statemachines/traffic-light-5.svg
---  

The diagram describes exactly the same behavior. Both state symbols for the state `red` refer to the same state, so our traffic light still has the same number of states, just its layout changed. In this simple state machine this doesn't really matter, but this can help you to create better layouts once state machines grow in complexity.


**State Names:** Selecting good names for states can help making state machine easier to understand, especially when the states map to phases of the thing we want to model, like _on_ and _off_ for a lamp, or _open_ and _close_ for a lock. However, sometimes it's not clear what a good name is. In such cases, I recommend to use state names like `s0`, `s1`,..., which can make life easier. You always have the possibility to attach a note to a state and explain what it means.



Please note:

- At any time, the state machine is in exactly one of the states. 
- State symbols with the same name refer to the same state. 

 
## Transitions

The arrows between the states are called **transitions**. We have said above that the state machine is at any point in time in exactly one of its state. It is not in two or more of them at the same time, and it is never somewhere in between. Conceptually, this means that a state machine switches from one state to another one within no time at all,  meaning that **transitions take no time**. This sounds magical, but we will come back to this.

So far, we have not yet talked about _when_ a transition happens, this means, what **triggers** a transition. We have, for example, not described _when_ the traffic light switches from `red` to `red_yellow`. There are three types of events that can trigger transitions in a state machine:

* The state machine is started, then its **transition from the initial state** is triggered. This happens when the component or code surrounding the machine is started and then starts up the machine, for instance when we boot our firmware and the software starts running.
* The state machine observes the **expiration of a timer**. Timers are managed by the machine itself, and we will learn how timers can be started and stopped later. 
* The state machine **receives a signal.** State machines can receive signals from other parts of the system, which can be code, drivers, interrupts or communication modules, or other state machines.

All transitions need to have exactly one trigger, because they would otherwise never be started at all. A trigger is declared using a label on the arrow, followed by a `/`. This means that you should have a trigger label at all transitions, with the only exception being transitions starting at initial states, because their trigger is implicitly the start of the entire machine.

A transition that starts at an initial state is also called _initial transition_.


## Actions

Let's have a look at a blinking light that you find often at the entry of tunnels. The light blinks with two lamps to indicate that the tunnel is closed. The blinking happens so that either the left lamp or the right lamp are on, and they switch every second.

---
type: figure
source: figures/statemachines/tunnel.jpg
---  

Now we also want to specify the actions to switch the individual lamps on and off. We assume that we have for this the actions `left_on()`, `left_off()`, and `right_on()`, `right_off()`. We already use Python syntax for these actions. In our state machine diagram we can use these actions and add them to the transitions.

---
type: figure
source: figures/statemachines/tunnel-1.svg
---  

The actions are also called an **effect** of the transition, and happen at the same instant the transition is executed, that means, when we switch states. The effects are written behind the `/` of the transition label.

* The state machine runs action `left_on()` when it starts, as declared by the initial transition.
* When the machine switches from state `left` to `right`, it runs actions `left_off()` and `right_on()`, separated with a `;`.
* When the machine switches from state `right` to `left`, it runs actions `right_off()` and `left_on()`, separated with a `;`.
* When the blinking light switches off and moves into the final state, we run actions `left_off()` or `right_off()`, depending on in which of the two states we are. 


---
type: figure
source: figures/statemachines/tunnel-2.svg
---  


Another way to execute actions is to add them to a state, and run them when we enter or exit the state. For some problems, such as the blinking light, this makes the diagram much easier. Have a look at the functionally equivalent diagram:


---
type: figure
source: figures/statemachines/tunnel-3.svg
---  


Here we have drawn the state symbol with a compartment (like a bookshelf) and add entry and exit actions to it. Actions that are preceded with the prefix `entry/` are executed when the state machine enters the state, and actions preceded with the prefix `exit/` run when the machine exits the state. In the example this cleans up the entire diagram, since we also can remove the actions from the initial transition and the transitions that target the final states. 

You can list as many entry and exit actions for a state, just add a new line with the prefix `entry/` or `exit/` for each of them. And of course, it looks nice when you list all entry actions above the exit actions. 



---
type: figure
source: figures/statemachines/many-actions.svg
caption: "Several entry and exit actions are possible."
---  



**Mind the Dash!** The dash on the transition labels separates the triggers from the actions. 

* For initial transitions (the ones originating at an initial state) that do not have an action, the label is empty. 
* For initial transitions with actions, we add the dash before the actions: `/a1(); a2()`
* For actions that do not start at the initial state, they need to declare exactly one trigger, followed by the dash. Optionally, they can declare actions as they need. For instance `t1/` or `t1/a1(); a2()`.
 




## Timers

The expiration of a timer can trigger a transition. By convention, we name timers with a prefix `t`, like for example `t0`. To declare that a transition is triggered by a timer, we simply write the name of the timer in the transition label. 

State machines manage timers on their own, wich also means that timers can only be started as part of an action within the same state machine. As we anticipate already our implementation inn Python, we use the following syntax for controlling timers:

* `start(t1, 1000)` starts a timer with name `t1` that will expire after 1000 milliseconds. If we invoke this action again while the timer is active and has not yet expired yet, the countdown will again start from the beginning, i.e., we expect the timeout 1000 milliseconds from the last call of `start(t1, 1000)`.
* `stop(t1)` stops a timer, so that a timeout will not happen in the future. In case this action is called but `t1` already expired or was never started before, nothing happens.

### Spaghetti Timer Example

Imagine we want to describe the behavior of a simple spaghetti timer. This timer expires after 10 minutes and then beeps for 3 seconds. We can do this with the state machine below.

---
type: figure
source: figures/statemachines/spaghetti-1.svg
caption: "Simple timer that beeps for 3 seconds after 10 minutes are over."
---  

Using entry and exit action on the states, we can also write this one in a more compact form.

---
type: figure
source: figures/statemachines/spaghetti-2.svg
caption: "Functionally identical timer, but with entry and exit actions on the state."
---  

**Exercise:** Simulate both of these state machines in you head or on paper by going through all the states, starting with the initial state. Verify that these to versions really are functionally equivalent.

## Internal Transitions

You have seen that we can declare entry and exit actions within a state symbol, which lets us in some cases describe more compact state machines. Another thing we can declare within a state is an **internal transition**. The internal transition has a label like normal transitions, `trigger/actions` but is written inside the state symbol, between the entry and exit actions. 

---
type: figure
source: figures/statemachines/internal-transition.svg
caption: "Declaration of an internal transition, triggered by event A."
---

The state _s1_ above declares an internal transition `A/a_2()`. It is triggered when the event `A` is happening. When that happens, action `a_2()` is executed. Because it is an internal transition, the entry and exit actions are **not** executed. Also, because the state stays the same, we can react many times to the event `A`. Whenever it occurs whiole we are in state _s1_, action `a_2()` will be executed.

**Note:** When you look at the entry and exit actions, you see that they almost look the same as an internal transition. And the notation is quite consistent, because the prefix _entry_ and _exit_ before the `/` really do describe when the action behind the dash is executed. But these are not transitions, just declarations of entry and exit actions.

## Transitions, Revisited

Now you have seen many kinds of transitions, and we can summarize all the different terms for them. Knowing these terms makes talking about state machines much easier when you design one together with other engineers. So we have the following transitions:

* An **initial transition** originates at an initial state. It does not declare a trigger, since it is executed immediately when the state machine starts.
* A **self-transition** is simply a transition that starts and ends in the same state.
* An **internal transition** is a transition that starts and ends in the same state, but which does not invoke any of the state's entry and exit actions. 
* An **external transition** is the type of transition that is _not an internal transition_. That means, a "normal" transition form one state to another, a self-transition, or an initial transition.



## Choice States 

In some cases, we want to have a choice in which state a transition should switch, based on conditions in data. As an example, let's look at the incomplete state machine below. It describes a part of a controller for a heater. In state `heater_on` we wait for 1 second for timer `t`, which triggers the transition towards the choice state. This choice state has two alternative branches, distinguished by two guards, in rectangular brackets. Think of them as an if-statement in a programming language. if the temperature is okay, we switch into state `heater_off`. If not, we take the else-branch and restart the timer, to check again in another 1000 milliseconds. 

---
type: figure
source: figures/statemachines/heater.svg
caption: "Part of a temperature controller, using a choice state with guards to make a decision."
---

Don't worry too much about what to write into the guard for now. This will get much clearer once we implement state machines in Python, where we implement the entire choice state with a Python if-statement. 

A choice state can have many outgoing branches. One of them must have a guard that is true, otherwise the state machine would be blocked. I therefore recommend to have an else-branch, which is true whenever none of the other branches is true. 

By the way: There is one imperfection with this machine: When the temperature is not okay yet, we re-enter the state `heater_on`, which means that we execute entry action `heater_on()` again. We assume here that it is programmed in such a way that this doesn't matter. An alternative is to add the action to both incoming transitions of state `heater_on`. 


## Ping Pong


Communication for handling complexity



unexpected events - nothing happens, discarded-


Rule: make sure that all transitions are triggered by something-





so far, we used diagrams to write down our state machine. instead we can also use a table. these are the columns. source state, trigger, effect, target state. this will be very useful when we will program state machines. 

entry and exit action
self transitions
internal transitions


initial state is not really a state, because we don’t wait in them





## A Physical State Machine Model

State machines are implemented in code and executed by a computer. To understand how a state machine works, you can also think of it as a physical machine, which executes almost like a mechanical clockwork. The figure below illustrates such a machine. 

---
type: figure
source: figures/statemachines/state-machine-machine.svg
caption: "An imaginary machine that illustrates how a state machine works."
---


The state machine has an input queue for signals sent by other parts of the system. These may be other state machines within the same computing node, state machines from other nodes, or other parts of programs that send messages.

All messages arrive and are sorted in a first-in, first-out (or short FIFO) order. 

The state machine also manages a set of timers. The state machine starts these timers as part of its behaviour. When a timer expires, it places an event in the same event queue as the one for incoming messages. Timer expiration events are placed at the front of the queue, since an event from a timer should be processed as close to its actual expiration time as possible.

The state machine interprets the state machine diagram. The diagram can be represented as a state-transition table. In this table is written down in which current state of the state machine an event has which effect. The effect means the behaviour the state machine is executing. This includes to start and stop timers, run operations, and moving the state machine into its next state. The state machine can also keep track of other data by using variables. (This is why this type of state machine is also called *extended* finite state machine.)


## Queue Semantics

To understand how a state machine executes, it is important to understand how the input queue works. 

* Messages arriving at the input of the state machine are placed at the
end of the queue.
* Time events are placed at the front of the queue when the corresponding timer expires.
* States can defer events.
* Events that are not consumed or deferred are simply discarded.


**Discarding events:** When the state machine is in a state that does not declare a transition that is triggered by the event at the head of the queue, the event is taken from the queue and discarded, that means thrown away.

<img src="https://www.iik.ntnu.no/ttm4115/wp-content/uploads/2018/02/Screen-Shot-2018-02-06-at-10.32.12-1024x365.png" alt="" width="750" height="267" class="alignnone size-large wp-image-358" />

In state *s1* above, for instance, *b* is not consumed. (The state machine is waiting for message *a*.) It is therefore discarded as soon as it arrives during state *s1*. Note that it is discarded even if it is consumed by the later state *s2*, which is not the current state.

<img src="https://www.iik.ntnu.no/ttm4115/wp-content/uploads/2018/02/Screen-Shot-2018-02-06-at-10.32.18.png" alt="" width="958" height="302" class="alignnone size-full wp-image-359" />

**Deferring events:** A state can *defer* some events. This means that the deferred events are ignored in this state. When a deferred event is at the head of the event queue, the state machine will act like it is not there, and process the first event that is not deferred. Once the state machine switches into its next state, the previously deferred event is not ignored anymore (unless also the next state defers it). Deferred events are written within the state symbol following the keyword */defer*.