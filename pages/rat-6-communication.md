## Question 1

:rat:Consider the code below.
In which line do you see a quite severe error, that shows that the developer has not read enough about MQTT?

1. Line 5
2. Line 4
3. Line 8
4. Line 9

---
type: figure
source: figures/rats/mqtt-listing.png
---


## Question 2

:rat:Why is it important for an MQTT client to disconnect properly from a broker,
that means, by telling the server explicitly instead of just dropping the connection?

1. To keep durable topic subscriptions once the client connects again.
2. To be able to reconnect at all.
3. To be able to reconnect using the same client Id.
4. To prevent that a configured last will is issued although the client is okay.

## Question 3

:rat:Have a look at the clients below. Which of them will receive a message, which is sent to the topic `ntnu/ttm4115/rat/communication`?

---
type: figure
source: figures/rats/mqtt-topics.png
---

1. 1 and 4
2. 1 and 3
3. 3 and 4
4. 1 and 2

## Question 4

:rat:Which of the following interactions can *not* be supported by MQTT?

1. Many subscribers can subscribe to the same topic.
2. Subscribers can subscribe to many topics.
3. Publisher and subscriber interact directly with each other.
4. Many publishers can send to the same topic.

## Question 5

:rat:Which QoS level is implemented by the interaction below?

1. QoS = 1
2. QoS = 0
3. QoS = 3
4. QoS = 2

---
type: figure
source: figures/rats/mqtt-qos.png
---

## Question 6

:rat:Which of the following is not a message pattern?

1. observe
2. client-server
3. publish-subscribe
4. request-response

## Question 7

:rat:What HTTP is to request-response, MQTT is to...

1. fire-and-forget
2. publish-subscribe
3. broker-subscriber
4. observe

## Question 8

:rat:What is a retained message?

1. A message that is lost between broker and subscriber
2. A message that is stored by the broker and pushed to a subscriber when needed
3. A message that is prevented from reaching the subscriber
4. A message that is published to a topic that has no subscribers

## Question 9

:rat:Which of the following is wrong?

1. Initially, HTTP was built to fetch resources such as HTML documents.
2. HTTP uses the request/response pattern.
3. The roles in HTTP are server and client.
4. In HTTP, only the server takes initiative.

## Question 10

:rat:The following are more composite and more reflective statements about MQTT and HTTP.
With which of them do you agree the most?

1. The advantage of HTTP is that only the server needs to know the protocol, the client side only requires a browser.
2. HTTP can only transport standardized documents like websites or images.
3. The different QoS levels in MQTT exist to handle different sizes of payload.
4. MQTT and HTTP are very different protocols, they are almost opposites of each other in many respects.
