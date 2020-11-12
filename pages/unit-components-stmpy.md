# Components


In this section, we want to study some of the technical solutions to create components with state machines that we can use for several applications.



# STMPY Components + MQTT

To ensure a **low degree of coupling**, we connect components only by means of MQTT as communication between them. This means, components can run wherever the MQTT broker is reachable, and they can communicate asynchronously.

The state machines alone would not make good components. They are too dependent on communication (here MQTT) and other coide that they interact with. For cohesion, we therefore combine state machines with an MQTT communication client into a single component. This enables technically **a better degree of cohesion**.

These means alone do not ensure a low degree of coupling and a high degree of cohesion.
A good component design depends on how we manage to group the functions we need for a system or application into the different components.
This means we still have to put the right functions into the right components, but having them communication-wise decoupled already helps. 


# State Machines as Sessions

So far, we have only looked at singe instances of state machines, because they controlled a single resource. 

* The kitchen timer was controlling a single hardware plug, and we hence had only a single state machine.
* The bus stop had a single button and signal light, which we could take care of with a single state machine.

In some systems, there are multiple resources to control. For instance, imagine a parrking lot with chargers for electrical cars. Each charger deserves its own state machine to keep track of the states of the car. Integrating all charging logic into a single state machine is not recommended --- the state machine would not be able to meaningfully track the state of each single charger.

And now imagine that the number of resources is dynamic, and changes at runtime. Imagine for example, that you have a management system for keeping track of customers in a recycling station, where you want to represent each customer with a state machine to keep track of their states from entering to exiting.

For such cases, we keep on using a single state machine per resource it represents.
But we add the possibility to create several instances of the same state machine, and address them with an id. Each state machine instance is then called a `session`. 

For our component model this means that a component manages usually state machine sessions, that means, potentially many instances of them.

