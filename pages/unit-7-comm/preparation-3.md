# MQTT

MQTT is a protocol that is based on the **broker** topology, and that
implements a **publish-subscribe** message pattern. MQTT was invented in
1999 by Andy Stanford-Clark from IBM and Arlen Nipper from Arcom. Today,
MQTT is an Oasis standard.




MQTT is often used in situations where events should be sent from many
sensors and broadcast to several applications. IBM and others for
instance use MQTT so that IoT devices can send updates into their cloud.
When Facebook introduced their Messenger application as a standalone
application, they also relied on MQTT to push messages to the
clients. We consider MQTT in detail because this protocol is
relatively easy to understand, introduces concepts that are used in
various form also in other protocols, and because its patterns and
topology is complementary to those of HTTP. When you have understood
MQTT and HTTP, many other application-level protocols will be easy to
understand, too. There are also some more practical reasons why we
recommend you to use MQTT for the semester project:

:aside: If you have a Facebook account, you may read the article [Building Facebook Messenger](https://www.facebook.com/notes/facebook-engineering/building-facebook-messenger/10150259350998920)



-   MQTT is simple to debug, since more than one entity can subscribe to
    the same topic. This means, you can work on the communication
    between two entities, but observe all communication by subscribing
    to these topics with a debugging tool.

-   You only need to handle the IP address of the MQTT broker. All other
    addressing happens indirectly via topics.

-   Application startup is simple. You can startup the MQTT broker
    first, but clients can then connect in any order after that. The
    MQTT broker can also be hosted on a server and be always-on.

-   MQTT works also behind a NAT, in both directions. This means you can
    push a message from any location to a computer that is connected to
    your router at home.

## Roles

There are three roles in MQTT. The **Publisher** sends messages to the
**Broker**, which then forwards them to a set of interested
**Subscribers**.

A typical interaction looks as follows:

---
type: figure
source: figures/mqtt-1.svg
---

There can be any number of subscribers and any number of publishers in a
system. Because of the publish-subscribe pattern, the subscribers do not
have to know about the publishers, and the publishers do not have to
know of the subscribers. They only have to know the address of the MQTT
broker and connect to it.

The brokers only implement generic functionality, this means, they do
not depend on the specific application. Therefore, the broker is a
component in a system that can be reused. There are several MQTT brokers
available. Examples are Mosquitto, RSMB, HiveMQ.

## Topics

Usually, subscribers are not interested in all messages that all
publishers send. Subscribers therefore only subscribe to specific
topics, which depend on the application. The topics are organized in a
hierarchy, separated by a dash ("/"). The following is an example for
topics that an application for home automation can use:

```
house/garage/lights/l1
house/garage/lights/l2
house/garage/sensors/pi1
house/garage/doors/d1
```

The light *l1* for instance subscribes to the topic
`house/garage/lights/l1` so that it can receive messages that switch it
on or off. The passive infrared sensor *pi1* publishes messages to the
topic `house/garage/sensors/pi1` every time it detects a movement. An
application to switch on the lights whenever a movement is detected can
then work like this: (In pseudo code)

```
subscribe to house/garage/sensors/pi1
whenever an MQTT messages arrives at house/garage/sensors/pi1:
    send a message 
        to house/garage/lights/l1 with payload "on"@
    
    after some time, send a message
        to house/garage/lights/l1 with payload "off"
```

Topics can include wildcards, which make it possible for a subscriber to
subscribe to several topics with a single pattern:

-   The "+" is used as a wildcard for a single level

-   The "\#" is used as a wildcard for several levels. It must only be
    placed at the end of a topic pattern.

Examples:

-   To receive all messages sent within the house, a subscriber can
    subscribe to `house/#`

-   To receive all messages for lights in any zone (garage or kitchen),
    a subscriber can subscribe to `house/+/lights/+`

### Exercise:

A publisher sends a message to the topic `a/b/c/d`. Which of the
following 15 subscription topics will receive this message?

---
type: table
file: tables/mqtt-questions.mw
class: table-sm table-bordered
format: html
---


   No. Topic  
   ---  ---   
   1   `#`                      
   2   `+/+/+`                  
   3   `+/+/+/+`                
   4   `+/b/c/#`                
   5   `+/b/c/d`                
   6   `a/#`                    
   7   `a/+/+/d`                
   8   `a/+/c/d`                
   9   `a/b/#`                  
   10  `a/b/c`                  
   11  `a/b/c/#`                
   12  `a/b/c/d/#`              
   13  `a/b/c/d`                
   14  `b/+/c/d`               
   15  `a/b/c/d/+`               

## Retained Messages

Imagine a temperature sensor that sends the temperature every 10
minutes. This is a sensible intervall, since temperature does not change
too quickly, and the sensor should preserve its battery. When we start
an application that needs the temperature in a room, it would have to
wait until the sensor sends its temperature, which can be as long as
about 10 minutes in the worst case.

---
type: figure
source: figures/mqtt-retained-1.svg
caption: "Scenario without retained message: The subscriber misses the last
update and has to wait until the next update is published."
---


Instead, the sensor can mark its temperature message as a **retained**
message. The broker will then store a copy of this message until it is
replaced with a new message sent to the same topic. Whenever a new
subscriber subscribes to the topic, it will immediately receive the
retained message from the broker. In our example this means that the
application does not have to wait until the sensor wakes up and sends
again, but that it immediately receives the last temperature reading.
(We show the reainted message with a trailing *R*.)

---
type: figure
source: figures/mqtt-retained-2.svg
caption: "Scenario with retained message: The subscriber misses the last update,
but receives the retained message from the broker."
---



## Last Wills

The MQTT broker monitors the connection to all clients, and detects once
they do not respond anymore. Any subscriber, however, by default does
not get notified once another client disappears. For instance, our
temperature application would not be able to detect immediately once a
temperature sensor disconnects. (It would only indirectly, because there
would be no temperature readings anymore.)

Instead, a client can define a "last will" with the broker at the
connection startup. This last will defines a message payload and a topic
to which the message will be sent if the broker detects that the client
suddenly disconnects. Any interested subscribers can then get notified
about the sudden disconnection. If the client, however, disconnects
properly from the broker, the last will message is not sent.

## Quality of Service

Messages can be sent with three different quality-of-service (QoS)
flags, which determine how much effort the broker and the clients spend
on sending them:

-   QoS=0 is also called *At most once*. The message can get lost, and
    there will be no attempts to resend it.

-   QoS=1 is also called *At least once*. This means that the message
    will be eventually received, but that several copies of the message
    may appear due to duplication. The receiver has to detect any such
    duplicates.

-   QoS=2 is also called *Exactly once*. This guarantees the delivery
    and avoids any duplication.

You may immediately ask: _If QoS=2 is available, why would one ever use
any of the lower QoS levels?_ The answer is that the highest quality of
service is also more expensive with regards to transmission effort. To
send a single QoS=2 message, several messages on the underlying channel
are necessary. Therefore, an application should always choose the lowest
QoS level it can work with. Below you see three diagrams that show how
many control packages are involved to just send a single MQTT message
with the different QoS levels. (The grey message arrows that start end end at the same lifeline illustrate only local operations, not communication.)

---
type: figure
source: figures/mqtt-qos-0.svg
caption: "To send one MQTT message with QoS 0, only two messages on the lower layer are necessary."
---

---
type: figure
source: figures/mqtt-qos-1.svg
caption: "To send one MQTT message with QoS 1, at least three messages on the lower layer are necessary."
---

---
type: figure
source: figures/mqtt-qos-2.svg
caption: "To send one MQTT message with QoS 2, at least five messages on the lower layer are necessary."
---



## Sequence Diagrams on Many Levels

Maybe you wondered how some of the sequence diagrams we have seen on the
last pages relate to those that you develop for a specific application.
Assume the application uses MQTT. What should you show then in a
sequence diagram? The answer: _It depends on what you want to show._

-   The diagrams **Quality of Service X** above show how MQTT is implemented internally
    and passes messages in order to publish one single message. These
    diagrams are only interesting when you need to understand if the
    MQTT protocol is suitable for your purposes, or you are concerned
    which QoS level to use. You will probably not use this level of
    detail for an application-level diagram.

-   The diagram above that shows MQTT using a retained message above
    is already closer to the application level, since *publish*,
    *subscribe* and *message* are shown as single, compact messages.

-   In some cases, it is probably interesting to show an MQTT broker as
    part of the sequence diagram. After all, it is a critical component
    in the system that requires consideration. But it may not be
    necessary to contain the broker in the diagrams of all use cases.
    Instead, the lifelines representing individual MQTT clients can
    directly send messages to each other, so that the application logic
    gets easier visible.

# Solution

       **Topic**                **Receive?**
  ---- ------------------------ --------------
  1    `#`                      yes
  2    `+/+/+`                  no!
  3    `+/+/+/+`                yes
  4    `+/b/c/#`                yes
  5    `+/b/c/d`                yes
  6    `a/#`                    yes
  7    `a/+/+/d`                yes
  8    `a/+/c/d`                yes
  9    `a/b/#`                  yes
  10   `a/b/c`                  no!
  11   `a/b/c/#`                yes
  12   `a/b/c/d/#`              yes
  13   `a/b/c/d`                yes
  14   `b/+/c/d`                no!
  15   `a/b/c/d/+`              no!
