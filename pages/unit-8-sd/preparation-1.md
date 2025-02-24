# Intuition on Sequence Diagrams

An important difference to state machines is that sequence diagrams
usually do not model complete behaviors, but only show selected
scenarios that a developer wants to show. More on that later. Let's
first get some intuition on sequence diagrams.

Sequence diagrams are an effective and intuitive way to describe the
communication between several communicating partners. Have a look at the
following dialogue:

---
type: figure
source: figures/intuition.png
caption: "A sequence diagram showing a conversation."
---

That's pretty much how sequence diagrams work, they show messages
between participants. Each participant in a sequence diagram is
represented by a vertical line, called *lifeline*. The horizontal lines
are messages. Time flows downwards, so that the messages make up a
conversation.

With this little knowledge, you can already understand most sequence
diagrams. What follows are refinements of this concept and additional
modeling elements so we can more precisely express how a software system
communicates. This is necessary to prevent misunderstandings between
developers and when we want to detect design flaws in our systems at an
early stage.

## Participants and Lifelines

Each participant in a sequence diagram is represented by a lifeline,
shown as dashed lines. It's okay to show them as solid lines, which may
sometimes be quicker when you make a sketch by hand. Lifelines are
always drawn parallel to each other, and follow a vertical orientation.
You will never see a sequence diagram with horizontal lifelines. If you
do, it's not a sequence diagram.

Lifelines can represent software concepts like components, modules,
objects or classes. They can also represent entities from reality, like
human users. The diagram below shows how a human user who presses a
button on a car key. The car key then sends a radio signal to the car,
which in turn confirms to the user by blinking the lights.

---
type: figure
source: figures/car-key.png
---

The top of the lifeline shows a box that refers to what the participant
represents in this sequence diagram. The label in this box consists of
three parts: a role name, a selector, a class name.

    role[selector]:Class

Let's look at an example to understand the difference between these.
Below you see a sequence diagram of a home automation system. There are
several **roles**: *sensor* and *light*. The role name is a name that
refers to the participant's function within an interaction. From the
lifelines that represent sensors, the diagram shows that there are two
**classes** of sensors, *TempSensor* and *HumiditySensor*. All of them
act as sensors in the system (and hence send signals with the name
*measurement*), which is why they all share the same role. All
components communicate with the central unit. Here we have chosen to
just give it a class name *HouseCentral*, since there is only one and we
already know that we want to have this class. An alternative would be to
just give it a role name, for instance *central*. You can also see that
the sensors have different **selectors**, which here are strings that
refer to different rooms. They show that there can be many sensors (role
*sensor* of the same class (for instance *TempSensor*). Here, room names
make sense. Alternatives are numbers.

---
type: figure
source: figures/home-system.png
---

A lifeline requires at least a role name or a class name. The selector
is optional. Note that the class name is always preceded by a colon
(":"). Usually, role names are in lowercase letters, and class names are
written in CamelCase.

## Messages

The horizontal arrows are called **messages**. They represent either the
transmission of a **signal**, or the **call of an operation**.

-   **Signals** represent information that is communicated
    asynchronously between objects. So far, all messages we have seen
    have referred to signals. They may refer to the physical touch of a
    button, a radio transmission, the signal of a light, a sound
    notification, or any other transmission of information. In the
    following, many of our signals will represent units of some specific
    protocol, like an MQTT or AMQP message. Signals are always
    asynchronous, and therefore use always the symbol for asynchronous
    messages, which is the solid line with an open arrowhead.

-   Alternatively, messages in sequence diagrams refer to **operation
    calls**. They correspond to functions, methods or operations in
    programming languages.

---
type: figure
source: figures/math-pow.png
---

The figure above shows an example of a sequence diagram that shows the communication
between a Python main program *main.py* that calls the *pow()* function
of the *math* module. As you can see, this interaction is much more
complicated than the one with the signals. An operation call consists of
two messages: the message that represents the call of the operation, and
another one that shows the return of the operation. In the example, the
operation also returns a result. The messages are also drawn
differently: The call message in this example is a synchronous message,
and therefore drawn with a filled arrowhead (as opposed to the open
arrowhead of the message that describes a signal). The return message
has an open arrowhead, but is painted with a dashed line. Therefore,
this is a synchronous function call, which represents what the Python
program actually does: The calling main.py is blocked (not doing
anything) while math.py is calculating the results and then returns.

Sometimes the return message is left away, to reduce the visual clutter
of a diagram or just due to laziness. In this course, we don't do that
for didactic reasons, so that we can clearly distinguish the modeling of
signals from that of operation calls. If you use messages that represent
operation calls, always draw the return messages.

---
type: figure
source: figures/math-pow-3.png
---

There are also situations where method calls in programming languages
are asynchronous. Then, the calling message is shown with the
asynchronous message symbol (the one with the open arrow head). In this
course, you will probably not use this and can forget about them.

---
type: figure
source: figures/math-pow-2.png
---

The diagram above shows another element that is sometimes used:
**execution specifications**. These elements illustrate that a
participant is active. For instance, the main program is active, then
calling *pow()*, which activates the math module until it returns. In
some cases, such an illustration is very helpful, for instance to
represent recursive method calls, or illustrate design patterns. In this
course, execution specifications are optional. In many situations it is
better to focus on the messages and get them right.

## Creation and Destruction

In some cases, it is interesting to show that a participant in an
interaction is created or destroyed as part of the interaction. This is
shown by special messages. Creation messages target the head of the
lifeline that they create. Destruction messages target a lifeline that
is then terminated with a big termination symbol. Both messages are
shown as dashed lines with an open arrow. They can be labeled with the
*create* and *destroy* stereotypes. The example below shows how the main
program creates an object of type *Socket* and then destroys it again.
Note that creation and destruction can be used independently, and that
they can be triggered by different participants in the interaction. A
lifeline can also terminate itself without a destruction message.

---
type: figure
source: figures/create-destroy.png
---

# What do Sequence Diagrams Represent?

Let's take a step back. You have seen that sequence diagrams can
represent a wide variety of interactions, and even include elements that
are not software. Within software, we can coarsely distinguish two
different focus areas covered by sequence diagrams:

-   **Local interactions** *within a program*, i.e., procedure, method
    or function calls.

-   **Distributed interactions** of a system that consists of *several
    components*, each running some programs.

Note that both local and distributed interactions are represented with
several lifelines. In the local case, they represent different code
modules, like Java or Python classes or modules. Within both of these
interaction groups, you can use asynchronous signals or synchronous or
asynchronous operation calls. This means, there can be local signals,
and there are also distributed operation calls.

Sequence diagrams typically only show selected scenarios of the
interactions in a system, and do not give a complete picture. That means
they do not show all the possible exchanges of messages of a real
system, but focus only on a few but interesting ones. This may come as a
surprise. If we want to do a good specification job, don't we have to
study *all* interaction scenarios? The problem is complexity. Sequence
diagrams can quickly grow, and a naïve attempt to cover all scenarios
just by writing them down results in specifications that confuse rather
than clarify. Important aspects of the model will drown in too many
details, and the value of modeling is lost. There are several solutions
to this dilemma:

-   We will complement sequence diagrams with state machines, which give
    a complete picture, but on a local level only.

-   You will learn how to select the relevant and interesting
    interaction scenarios that deserve attention, and leave out those
    that are not relevant.

-   We will try to build interactions in such a way that the number of
    possibilities is reduced.

One way of making sequence diagrams more powerful and let a single
diagram express more than one scenario is by using combined fragments,
which we will look at in the next section.

---
type: nav
next: ["Combined Fragments", "preparation-2.html"]
---
