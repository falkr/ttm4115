# Communication


The deployment diagram below shows today's setup:

---
type: figure
source: figures/interactions/mqtt-setup-1.svg
---

The setup consists of at least three components:

* The MQTT Broker: This is ideally your own MQTT broker, but can also be a oublic MQTT test broker. 
* MQTT.FX: This is a generic MQTT client that is suitable for debugging MQTT-based applications. you can connect to an MQTT broker and subscribe and publish to topics.
* Jupyter Notebooks: We use MQTT client in notebooks to show you how to program in Python. 


## Tips for This Unit

* Document your progress and the result of all experiments in a document. 
  * Deliverthe document on Blackboard at the end. 
  * Include screenshots
* The tasks don't require much engineering work this week, so you have enough time to care about the details and the setup.
* Most tasks are related to running code, which can be difficult in teams of 6. 
  * This requires special attention from the facilitator. 
  * Make sure everyone is on board. 
  * Distribute tasks, but make sure everyone covers all. 
  * Try to work distributed on several PCs for the communication task. (You can run Broker, MQTT.FX and Python iáll oon different computers or on the same one. We recoomend to try the distributed solution.)
* Dare to ask questions, or repeat individually. 
* The programming tasks are important for the remainder of the course.

# Task: Running MQTT.FX

MQTT.FX is a desktop application that connects to an MQTT broker and that can publish and subscribe to arbitrary topics.
This is a very tool useful during development.
(If you wonder, the name _MQTT.FX_ just comes from the fact that it is implemented in Java FX, but you can forget about that.)
Using MQTT.FX is really simple, but because we have now talked about brokers, clients, publishers and subscribers, you may loose track and wonder what this MQTT.FX does: Think of it as a debugger for MQTT, and you can use it like Wireshark. Once the system is done, you don't need MQTT.FX anymore.

Essentially, MQTT.FX is a MQTT client, and can as such connect to an MQTT broker, subscribe to topics and send messages to topics. This does not sound like much. However, MQTT.FX has a generic user interface, you can use MQTT.FX while you construct your application to see how the other system components publish messages, and you can also "inject" messages into the system, by publishing to any topic you want.

<a class="arrow" href="https://mqttfx.jensd.de">Download MQTT.FX</a> 

---
type: figure
source: figures/mqtt/mqtt-fx-publish.png
---

### Publishing Messages

Imagine you have created a MQTT client that runs a certain action when it receives a message, but you are not doen with the component that should send the message. To test at least the component that should receive the message, you can use MQTT.FX to publish a message with that content to the topic, and the component under test will behave as if the message was sent in the final system.

---
type: figure
source: figures/mqtt/mqtt-fx-subscribe.png
---


### Observing Communication

Because MQTT uses the publish-subscribe pattern, it can simply subscribe to any topics that are interesting in your application  and you can see which messages are sent to these topics, without disturbing the communication in the system. To achieve the same in HTTP, for instance, you need a tool like Wireshark.


## Task: Obsrving a Public MQTT Broker

There are some public MQTT brokers to which anyone can connect. 

<a class="arrow" href="https://github.com/mqtt/mqtt.github.io/wiki/public_brokers">List of Public MQTT Brokers</a> 

* Connect MQTT.FX to a public MQTT broker. (I usually use the MQTT broker of the Eclipse IoT project, with the address `iot.eclipse.org` and port `1883`.)
* Subscribe to topic `#`
* Have a look at the incoming messages, the topic they are sent to, and their payload.




# Task: Running Your Own MQTT Broker

You can alsways use such a public broerk for testing, but on most cases it is better to have your own broker running. 
Install the **Mosquitto MQTT Broker** on your laptop. This is an open-source MQTT broker that is relatively easy to install and run. 

* Install Mosquitto from [https://mosquitto.org/download/](https://mosquitto.org/download/)
* Start it locally. You can use it with the option `-v` (verbose) so that it prints more information.
* Test how the broker works by connecting to it with MQTT.FX, as explained above.
* Try to have the MQTT broker on one PC, and communicate with other PCs that have MQTT.FX running.
  * For that to be possible, you need to be able to ping the PC that runs the broker.
  * You need to be on the same network.
  * If nothing works, you can also have MQTT.FX and the broker installed on the same PC, and use address `localhost`.
* If you have trouble installing Mosquitto, try to find help woth others on MS Teams!



# Task: Python Notebooks

Now we are going to combine what we learned about MQTT with Python. 

* Download the latest version of the repository with the [STAMPY notebooks from Github](https://github.com/falkr/stmpy-notebooks).

## MQTT Part 1 - Connect to Broker

This notebook explains Paho, the Python client for MQTT and connects to a broker. 

## MQTT Part 2 - Connect and Publish

This notebook extends the MQTT client and also publishes messages, forwarding to another topic.

## MQTT Part 3 - MQTT and STMPY

This notebook shows you how to connect the MQTT client with state machines in STMPY.


# Checklist

 

### Blackboard

- Deliver your document that shows progress and results. 

### MS Teams

- Ask for feedback in general
- Report any errors with the provided solution
- Discuss, with me or other teams

### Team Reflection for This Unit 

* Add another section to the team reflection document, just like every week. 

### Individual Reflection

* Fill out the <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=cgahCS-CZ0SluluzdZZ8BSxiepoCd7lKk70IThBWqdJUQUQxNEVLOTBZMDZGNkJBM1Y2NjZCTzhWSi4u" class="arrow">individual reflection survey</a>.
* Copy the answers into a document that you maintain on your own.
* Add any additional observations to your reflection diary.



