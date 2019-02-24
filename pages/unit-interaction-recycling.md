# Recycling Park

---
type: figure
source: figures/interactions/heggstadmoen-photo.jpg
---


A recycling park is an area where people can deliver all sorts of special waste, like wood, scrap (old metall), gardening waste, electric devices, batteries and general waste. Some waste is free to deliver, and some waste is subject to a charge. The recycling park is therefore split in two areas: The first area has parking spaces where people can park their car and get rid of the free waste types. The second area is for the paid waste.

---
type: figure
source: figures/interactions/heggstadmoen-map.jpg
---

## Technical Installation 

The area for the payed waste has a gate at its entrance and a gate at its exit. The gate has lights (red or green) and an arm that can open to let a car drive through. The gates are combined with big weight scales integrated into the road where an entire car can drive on. With them, the weight car can be measured before and after. At the entry and exit, customers swipe their credit card. Note that they swipe it also at the entry, and the credit card number is used to identify a customer on their way out, so that entry and exit weight of the same customer can be compared.


## Goals and Functions

The system must serve two main goals:

1. The number of cars within the payed area is limited to 30 cars at a time.
2. Cars are registered with their weight at the entrance and exit, and customers are billed for the waste according to the difference of their car's weight.

Other functions of the system can be to record detailed statistics about the number of cars each day, and figure out the most busy visiting times. But these functions are not relevant now.


## Communication and Deployment

It's a modern installation. All units (lights, weights, gates, card readers) are connected to an IP-based communication bus (Wi-Fi or Ethernet). There is a central computer in the recycling park that runs the application to connect the system. It can send and receive messages with the different units.


## messages

Let's have a closer look at the messages that all the deployed units can send. The suffix `_x` behind the message names can be replaced with (`_1`) or (`_2`), to address the units at the entry (`_1`) or the exit (`_2`). We do not show the format of any values that the messages may carry (like image format or weight or payment unit), you may ignore these details.

The **gate** simply opens for a while so that a car can pass through when it receives the message `OPEN_x`.

The **lights** are either red or green. Green means that the customer can drive in, red means that they have to wait, either for weighing the car, processing the payment or because too many cars are already in the area. The light can be controlled with the messages `RED_x` and `GREEN_x`.

The **weight** is place before the gate. To make a reading, the message `GET_WEIGHT_x` can be sent to the weight. It then answers with the message `WEIGHT_x`. (This message includes the weight as a value.)

The **card reader at the entry** registers a credit card at the entry. Once a customer arrives, they swipe their card. message `CARD_x` is sent, and it includes the card number.  

The **card reader at the exit** register a credit card once a customer wants to exit. They swipe their card, and the card reader sends message `CARD_x`.

The **payment service** is an online web service. For simplicity we assume it is also reachable via messages. Assume it accepts messages `PAY` when a payment should be made, and it answers with message `PAY_OK`.

We assume in the following that all payments are okay, both weights work perfectly, and all customers behave nicely. We also assume that customers do not mix up their cards, i.e., only card that have been swiped at the entry are used at the exit.


## Task: Car Entry

Develop the sequence diagram **Car Entry** that shows how a car enters the payed area. Assume that no messages are lost and all components are working well.

Cover the following lifelines:

* `gate_1: Gate`
* `lights_1: Lights`
* `card_1: Card Reader`
* `w_1: Weight`
* `c: Computer`


## Task: Car Exit

Develop the sequence diagram **Car Exit** that show hows a car exits the payed area. Assume that no messages are lost and all components are working well.

Cover the following lifelines:

* `c: Computer`
* `p: Payment`
* `gate_2: Gate`
* `lights_2: Lights`
* `card_2: Card Reader`
* `w_2: Weight`

## Task: Complete Single Visit

Using the two existing diagrams, develop one that specifies the complete visit of a single car. Use the following ordering of lifelines:

* `gate_1: Gate`
* `lights_1: Lights`
* `card_1: Card Reader`
* `w_1: Weight`
* `c: Computer`
* `p: Payment`
* `gate_2: Gate`
* `lights_2: Lights`
* `card_2: Card Reader`
* `w_2: Weight`


## Task: Robust Car Entry

Create a new sequence diagram **Robust Car Entry** that is an improved version of the original diagram. Assume now that pretty much everything can fail:

- components can break down
- operations in the components can fail
- messages may be lost 

Look first at the original diagram and think about how the behavior can be improved so that the system handles errors "a little bit better." (What that means in detail is up to your interpretation.) You may for instance introduce additional messages and timers. Show timers as messages sent from a lifeline back to itself. **Briefly document your reasoning as comments in the diagram.**


# Today's Delivery

* Create a single PDF with all diagrams from today.
* Filename must be `ttm4115-2019-TA-interactions-TXX.pdf`, where `XX` refers to your team number. 
* Complete the Team Reflection, and copy the content into your [Team Reflection Document](team-reflection.html)
* Clean up the working area.
