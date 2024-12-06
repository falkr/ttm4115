# Communication Protocols

Communication protocols easily fill a course on their own, because
there are so many of them and because they rely on a lot of mechanisms
that are worth studying. You have probably already learned about
protocols like TCP and HTTP. In the following, we will have a look at
protocols from the viewpoint of an application. From this perspective,
we are concerned with the entire system, the user requirements and also
the development process to build that system.

---
type: figure
source: figures/wifi_vs_cellular.png
caption: "Communication fails, and we are used to it. From XKCD, https://xkcd.com/1865/"
---

Communication between components has a great influence on the system,
its performance, its behavior, its robustness and its security, to name
a few. Communication is probably most brittle part of our logic, since
it depends on many factors that we don't have control over. For
instance, communication can *always* fail, either because the
communication channel has errors, or our communication partner failed.
Communication often takes a long time compared to local operations that
we have more control over. We are never sure about the state of our
system until we receive something back.

There are different strategies to integrate the challenges with
communication into an application. In most cases, you will not implement
all communication logic from scratch, but use a library, for instance to
make an HTTP call or accept incoming UDP packages. This of course
simplifies the implementation. Once a library for communication gets
very advanced and introduces assumptions about your architecture, we
also call them a framework or a middleware. There are communication
frameworks that use more basic communication mechanisms, add logic on
top of them and offer simpler application development. They take for
instance care of some failure management and guarantee some system
properties. They may also provide a uniform interface to several
protocols, so that it is, for instance, possible to talk to other
components no matter how they are connected. However, we still need to
take into account that communication fails, may have to re-send
messages, or tell the user that something is wrong. So even good
middleware, libraries of framework don't free you from the problems of
communication; they may however, make life much easier.

---
type: figure
source: figures/communication-errors.jpg
---

Let's have a look at three very different applications:

-   A wireless **temperature** sensor sends the temperature every ten
    minutes to a receiver that logs the temperature. The communication
    in between the two uses some wireless protocol, for instance
    Bluetooth or Zigbee. In this case, it may be appropriate to not do
    anything specific when the transmission fails. A failed transmission
    means one data point less, which may be acceptable. Of course, the
    user should see somehow if the communication works most of the time,
    for instance by showing how old the last measurement is and maybe
    blinking as a conformation when a new measurement was received.

-   An electronic **body weight scale** offers automatic logging to an
    iPhone app via Bluetooth. Here, each measurement is more valuable to
    the user, since they make this measurement less often and want to
    log it. However, also here the communication can fail, for instance
    when the phone is out of reach or Bluetooth is turned off. Like with
    the temperature sensor, communication could simply fail, possibly
    also notifying the user. A more advanced handling is to store the
    value that has not been transmitted and send it once the phone is in
    reach again next time.

-   A third example is a **home automation system**. Here it can be much
    more critical to handle communication properly, as for instance
    activating monitoring remotely. Existing systems often use several
    communication channels at the same time. By default, commands from a
    remote user can be sent from their mobile phone over the alarm
    company's servers using the broadband connection of the house. The
    broadband connection is subject to failure. If the first sending
    fails, the app tries to send once again. At the same time, the
    command is put into a queue and the user can continue to use the
    app. If the sending fails once again, the app can switch
    communication modes an try to send the command as a coded SMS to the
    home gateway directly, since it also has its own mobile connection.
    Since, however, the user has to pay for this service, the app asks
    the user if the command should be sent this way.

All of these applications can be based on the same protocol, but on
their application level they handle communication very differently. The
temperature sensor offers no special logic, and just accepts
communication to fail. The body weight scale offers some compensation
that seems reasonable. The home automation system escalates the failure
and involves the user to make decisions, simply because the command is
important to transmit.

# Basic Terms and Mechanisms

Communication protocols determine rules that lets two or more entities
communicate with each other. They describe, for instance, how data is
serialized, how data is encrypted, or how errors are handled. In the
following, we look at communication by starting with the different
message exchange patterns, and study the different topologies. But
before that, let's look at some basic terms and concept that make things
easier to understand.

Communication happens between **components**, which are simply parts of
the system. Depending on how many details of a system we know, or on
which level of detail we want to describe it, a component can be
different things. It can be an application, a web server, a web browser,
or a device.

Roles during communication: A **sender** is the originator of some
communication, and a **receiver** accepts the communication. In many
forms of communication, a component can be both sender and receiver, and
depending on the pattern there can be several senders or receivers. When
we want to express who started (or *initialed*) a communication, we
refer to that role as the **initiator**.

Components communicate via **interfaces**. These are simply some defined
points in a system dedicated for exchanging information. Depending on
which protocol of communication an interfaces uses, it can be described
in different ways, and more or less formal or detailed. An interface
description can tell other components for instance *"You can connect to
me using HTTP at port 80, with the following paths. I will return\..."*
Interfaces are also often called **APIs**, which stands for *application
programming interface*.

When communication happens, several mechanisms need to be in place and
known to all communication partners:

-   **Serialization** means to transform some piece of data, like a
    number or a name or a record of more complex data, into a series of
    bits and bytes. This is necessary since we only can send zeroes and
    ones over a wire or through the air.

-   **Cryptographic operations** to the data means to sign the data,
    secure it against changes or encrypt it to prevent others from
    reading it.

-   **Error handling** includes to add checksums, so that corrupted data
    can be detected and to add sequence numbers to detect missing data
    or duplicate data. This also includes strategies for the
    communication partners for when errors are detected.

Most protocols describe the transmission of data in chunks of bytes.
Depending on the protocol, these chunks are called *packets*, *frames*,
*messages* or *datagrams*. All of them have some body, also called the
payload, which contains the bytes to transmit. The body is enclosed by a
header and a tail, which contain information to control the protocol
mechanisms, like sequence numbers and checksums.

## Communication Layers and Stacks

Protocols often rely on other protocols to do their job. For instance,
HTTP uses TCP, which in turn uses the IP protocol. The protocols build a
communication stack, which each protocol adding some new
functionalities, also called *services*. For instance, IP offers
connectivity between networks using IP packets. TCP uses this
functionality and offers guaranteed delivery over the lossy IP channels
using a sliding window mechanism. HTTP then uses TCP to handle requests
that are ideal for websites, and was later also used for REST-ful APIs.

# Communication Topologies {#topologies-architectures}

With topologies, we describe the patterns of the nodes and summarize
some of their behavior. The following are the most important topologies:

**Client-server:** The client knows the address of the server. The server gets to know
the client only after the client makes initial contact. Since only
the client knows the address of the server initially, it is only the
clients that can make the first contact and take initiative. In the
world wide web, servers can host web sites and are contacted by
browsers (the clients.) This is an example where there are many
clients and only few servers, and where servers are optimized to
server many clients. But there are also protocols in which the
server is on a tiny sensor device, and "serves" the values of the
sensor to any client that is interested in them.

[Client-Server on Wikipedia](https://en.wikipedia.org/wiki/Client%E2%80%93server_model)

**Peer-to-peer:** A peer is a node in a communication scenario. The word peer
emphasizes that the nodes are equivalent, and each node can both
send and receive messages, that means the communication is
symmetric. This is in contrast to the client-server model, where the
communication roles are very different (also called asymmetric).
Peer-to-peer topologies are often used for applications where logic
is distributed among several nodes, often without a central node for
coordination. Examples are peer-to-peer networks for sharing data,
or the protocol for the interactions used in blockchain protocols
and currencies like Bitcoin.

<a class="arrow" href="https://en.m.wikipedia.org/wiki/Peer-to-peer">Peer to Peer on Wikipedia</a>


**Broker:** A message broker is a server that distributes messages. The message
broker usually does not care about the specific application or the
content of the message. Clients communicate with the server and send
messages to the broker, which then get distributed to those clients
that are interested in the events.

<a class="arrow" href="https://en.m.wikipedia.org/wiki/Broker\_Pattern">Broker on Wikipedia</a>

# Message Exchange Patterns

Communication happens by sending messages. Communication patterns
describe in which sequence and directions messages are sent to
communicate. Many protocols use similar message exchange patterns.

## Pattern: Single Message {#single-message}

The simplest pattern is a single message, sent from the sender to the
receiver. The message can contain data or be empty.

---
type: figure
source: figures/single-message.svg
---

Communication channels can be disturbed or disrupted, and messages can
get lost.

---
type: figure
source: figures/single-message-lost.svg
---



## Pattern: Request-Response {#request-response}

The requestor sends a message, and the responder sends a response
message back to the requestor. The response can contain data or be
empty. The answer message or response is also called *acknowledgement.*
The entire request-response pattern is also called *a handshake.*

A typical example is when a browser requests an HTML document from a
server. The request contains the address of the page and parameters. The
response contains the HTML document.

When it is important that a message is received, the request-response
pattern is often used instead of a single message. The reception of the
response is a confirmation to the requestor that the request was
received. In such cases, the request-response pattern is often combined
with a timer on the requestor side. If the requestor does not receive a
response within a given time, it sends the request again, until it
receives the response.




In a *synchronous* communication, the sender and the receiver are
directly connected, in the sense that the sender is not doing anything
else while the communication is going on. A synchronous
request-response, for instance, looks as follows:

:aside: Note that we are now using the words synchronous and asynchronous 
for the communication pattern, not to the specific modeling element
of a synchronous or asynchronous messages in sequence diagrams. In 
both examples, we use synchronous messages.

---
type: figure
source: figures/sync.svg
---

In contrast, *asynchronous* communication means that the sender and the
receiver are decoupled. The sender can do other things while waiting for
a response, or it may not wait for a response at all.

---
type: figure
source: figures/async.svg
---

## Pattern: Observe {#observe}

An observer can tell a server that it would like to get informed about
events. Whenever the event happens, the server notifies the observer
with a message.

---
type: figure
source: figures/observer.svg
---

## Pattern: Publish-Subscribe {#publish-subscribe}

The publish-subscribe pattern is similar to the observe pattern, but
involves three roles: a publisher, a message broker, and a subscriber.
The broker sits in between the publisher and subscriber. It has the
effect that publisher and subscriber do not have a direct connection
with each other, each of them is only connected to the broker.

---
type: figure
source: figures/publish-subscribe.svg
---


## Pattern: Exclusive Pair {#exclusive-pair}

This is the most complicated and also most general pattern. Here the two
communication partners have a specific sequence of messages to get a
specific job done, which depends on a specific application. The two
communication partners execute a longer negotiation or conversation.

### Example: Application

A mobile route planner application is an example. To get the shortest
route, a user first has to set the destination, the start and send it to
the route planner on a server. The route planner can then offer
alternatives, and the user selects among them, before the navigation can
start. This requires an interaction of signals in a specific sequence,
and the application and the server exchange information in that specific
sequence. For the duration of the interaction, they engage in an
exclusive pair interaction. Note, however, that the API in these
examples is often structured so that this interaction decomposes into a
series of request-response interactions coordinated by the application.

### Example: TCP

TCP is a protocol to provide a connection over a lossy channel (like the
internet). It handles that packages are lost, duplicated, or arrive in
the wrong order. To an application using TCP, these mechanisms are
invisible and it appears as if the connection simply works. TCP achieves
this by the rules according to which it sends the different messages in
both directions. So in this sense, two components talking TCP are an
exclusive pair that together execute a specific protocol.

# HTTP - Hypertext Transfer Protocol

This is only a very brief description of HTTP to relate it to the
previously described communication topologies and message patterns. You
have probably already heard about HTTP in other courses. Here, we look
at it from an application's perspective. If you are interested in more
technical details, read for instance on [Wikipedia](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol).

HTTP is a request-response message pattern, and uses a client-server
topology. The server usually provides resources to the client, which can
be a web browser. In HTTP, the initiatives for communication are
uni-directional. This means, the client takes initiative and contacts
the server, not the other way round. For the original purpose of HTTP
(requesting documents from a server) this is suitable characteristic,
since it simplifies the construction of efficient servers and how
documents can be cached.

## Getting Bi-Directional  {#getting-bi-directional .unnumbered}

One websites should get more interactive, this is a limitation we are
all aware of. We are used to refresh a website to see if there is new
information available. And when booking a flight or paying via credit
card, you see clumsy messages like "Don't reload this page." This is so
inelegant because technology was never intended to this stuff with a
browser! With this example you also see which fundamental effect
communication topologies and message patterns have. Websites today are
incredibly more advanced than ten years ago. Still, some of these old
limitations are hard to get rid off.

There are some mechanisms that work around these limitations of HTTP. If
you are interested in the details, have a look at the [Wikipedia article
on Comet](https://en.wikipedia.org/wiki/Comet_(programming)). To keep it brief; it's fascinating, but ugly. In essence,
the workaround is that the client still initiates all communication, but
client and server keep an HTTP connection alive, so that the server can
send updates once there are some. When Google offered chat on their
Gmail website, for instance, they used this mechanism to [push new chat
messages immediately from the server to the browser](https://stackoverflow.com/questions/732705/how-is-gmail-chat-able-to-make-ajax-requests-without-client-interaction). Google Docs
uses a [similar mechanism](https://stackoverflow.com/questions/35070217/what-technology-does-google-drive-use-to-get-real-time-updates).

To address the needs of server to notify the client when new information
is available, the [WebSocket protocol](https://en.wikipedia.org/wiki/WebSocket) was built. Like HTTP, it also
builds upon TCP, but offers full-duplex. With WebSockets, you can for
instance build relatively simple web-applications running in the browser
that support fine-grained, bi-directional interactions like chat or
games.
