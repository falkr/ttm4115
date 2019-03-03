---
status: draft
---

# MQTT

# MQTT Broker

<h2>Hosting your own MQTT broker</h2>
Hosting your own MQTT broker on a Raspberry Pi, by using Mosquitto:

All commands needed for the Pi are marked in <strong>bold</strong>

Start by making a new directory for Mosquitto:

<strong>mkdir mosquitto</strong>

<strong>cd mosquitto/</strong>

Now get a key and add it:

<strong>wget http://repo.mosquitto.org/debian/http://repo.mosquitto.org/debian/mosquitto-repo.gpg.key</strong>

<strong>sudo apt-key add mosquitto-repo.gpg.key</strong>

Make repository available to apt:

<strong>cd /etc/apt/sources.list.d/</strong>

<strong>sudo wget http://repo.mosquitto.org/debian/mosquitto-stretch.list</strong>

Now update the package-lists and install mosquitto:

<strong>sudo apt-get update</strong>

<strong>sudo apt-get install mosquitto</strong>

You should now have a working MQTT broker! (This broker listens on port 1883 by default)
<h3>Quick test</h3>
If you want to test this, it can be done easily by installing Mosquitto MQTT-clients aswell:

<strong>sudo apt-get install mosquitto-clients</strong>

You can now try to subscribe to a topic

<strong>mosquitto_sub -d -t example_topic</strong>

and publish something on that topic:

<strong>mosquitto_pub -d -t example_topic -m "Time for a coffee"</strong>

<img src="https://www.iik.ntnu.no/ttm4115/wp-content/uploads/2018/02/mqtt_example-300x231.png" alt="" width="525" height="404" class="alignnone wp-image-368" />


# MQTT in Python

After setting up your broker, you can easily make use MQTT in Python with the paho-mqtt package. To install this package with pip, use the command:

    python -m pip install paho-mqtt

We can now make a simple script that is able to <strong>publish</strong> information on a topic, to the broker:

```python
import paho.mqtt.client as mqtt
port=1883

def on_publish(client,userdata,result):
    print("data published \n")
    pass

client1= mqtt.Client("test1")
client1.on_publish = on_publish
client1.connect(broker,port)
ret= client1.publish("mqtt_test","The broker is working properly")
```

Now we need a **subscriber** to connect to the broker and recieve the messages we publish:

```python
import paho.mqtt.client as mqtt
    def on_connect(client, userdata, flags, rc):
    print("Connected with result code "+str(rc))

client.subscribe("mqtt_test/#")
def on_message(client, userdata, msg):
    print("Topic: " + msg.topic)
    print("Message: " + str(msg.payload))

client = mqtt.Client()
client.on_connect = on_connect
client.on_message = on_message

client.connect("192.168.10.168", 1883, 60)

client.loop_forever()
```


More information on the paho package can be found here: <a href="https://pypi.python.org/pypi/paho-mqtt/">https://pypi.python.org/pypi/paho-mqtt/</a>


If there is an error in the `on_message()` function, you may not see an error and nothing is happening, and it may look as if the client doesn't receive any messages. To prevent such errors, add a `print('Message received!')` line at the start of the message so you see it was called. Make sure this first statement does not have any problems (like unkown variables) so that it does not fail. 

You can also place any code that could cause an error into a `try:` ... `except:` block to handle any exceptions locally.




## Subscribe to system messages

client.subscribe("$SYS/#")



# Debugging With MQTT.FX

MQTT.FX is a tool useful during development.
(If you wonder, the name _MQTT.FX_ just comes from the fact that it is implemented in Java FX, but you can forget about that.)
Using MQTT.FX is really simple, but because we have now talked about brokers, clients, publishers and subscribers, you may loose track and wonder what this MQTT.FX does: Think of it as a debugger for MQTT, and you can use it like Wireshark. Once the system is done, you don't need MQTT.FX anymore.

Essentially, MQTT.FX is a MQTT client, and can as such connect to an MQTT broker, subscribe to topics and send messages to topics. This does not sound like much. However, MQTT.FX has a generic user interface, you can use MQTT.FX while you construct your application to see how the other system components publish messages, and you can also "inject" messages into the system, by publishing to any topic you want.

<a class="arrow" href="https://mqttfx.jensd.de">Download MQTT.FX</a> 

---
type: figure
source: figures/mqtt/mqtt-fx-publish.png
---

## Publishing Messages

Imagine you have created a MQTT client that runs a certain action when it receives a message, but you are not doen with the component that should send the message. To test at least the component that should receive the message, you can use MQTT.FX to publish a message with that content to the topic, and the component under test will behave as if the message was sent in the final system.

---
type: figure
source: figures/mqtt/mqtt-fx-subscribe.png
---


## Observing Communication

Because MQTT uses the publish-subscribe pattern, it can simply subscribe to any topics that are interesting in your application  and you can see which messages are sent to these topics, without disturbing the communication in the system. To achieve the same in HTTP, for instance, you need a tool like Wireshark.