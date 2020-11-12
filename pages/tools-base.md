# The TTM4115 Base Architecture

To make the development of the semester project simpler for you, we have developed a base architecture.

* **MQTT** is the protocol to connect all system components. We use Mosquitto as broker.
* **STMPY Components** provides support for state machines that communicate over MQTT. Internally, STMPY Components uses **Paho for Python** as MQTT client for Python and STMPY to drive the state machines.
* **Node RED** is a flow-based programming tool based on Node and Java Script. It connects with MQTT, and can help you to add data base components and to connect other hardware.
* **Paho for Java Script** can connect webpages that run Java Script to MQTT by using Websockets. This makes it possible to integrate two-way interactive websites into your system.