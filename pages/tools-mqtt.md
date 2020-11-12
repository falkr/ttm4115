# MQTT

We use MQTT as the protocol to connect all system components.

# MQTT Broker

## Install Mosquitto on a Raspberry Pi


### Mosquitto Broker

```bash
sudo apt-get install mosquitto
```

### Mosquitto Command-Line Clients

```bash
sudo apt-get install mosquitto-clients
```

### Testing Mosquitto

You can now try to subscribe to a topic

```bash
mosquitto_sub -d -t example_topic
```

and publish something on that topic:

```bash
mosquitto_pub -d -t example_topic -m "Time for a coffee"
```

<img src="https://www.iik.ntnu.no/ttm4115/wp-content/uploads/2018/02/mqtt_example-300x231.png" alt="" width="525" height="404" class="alignnone wp-image-368" />

### Enabling Websockets

If you want to connect to the MQTT broker also via MQTT over websockets (usually from Javascript) then you need to enable Websockets. For that, create a file called `mosquitto.conf` in the folder `/etc/mosquitto/conf.d` and add the follwing lines:

    listener 1883
    protocol mqtt
    
    listener 1884
    protocol websockets



# NTNU MQTT Broker

We have setup an MQTT broker with the address `mqtt.item.ntnu.no`. It is configured with the default ports `1883` for connections via TCP and `1884` for connections via websockets.

    listener 1883
    protocol mqtt
    
    listener 1884
    protocol websockets




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