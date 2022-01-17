# Semester Project


In contrast to previous years, we constrain the type of system that you should build. The reason for this is that many students find it hard to come up with a good idea that isn't too similar to what we already had. In addition, this has the benefit that you are more focused and interested when providing feedback to the other teams, as they try to solve a similar problem. 

We sill expect that there is enough variation in your priorization, selection, interpretation and implementation of the system functionality that you all end up with different systems. 


# 2021: Digital Walkie Talkies

The base idea is to create a communication device for workers. 

The core functionality is to send short voice messages to another colleague, without waiting for the colleague to take the call (there is no "call"), just by somehow selecting the receiver, recording a message and sending it. 

Such a function is also called _push-to-talk_ communication, and you probably know it from the way the crew members communicate on Star Trek.


## Robust, Reliable, Responsive

The most important feature of your system should be its reliability in all circumstances. 
This means, that it does not loose a message, but would try to reach a receiver and only if there's no other way to deliver the message tell the sender about it. 

The system should also be designed so that several messages arriving at the same time are handled somehow. 

At all times, the sender and the receiver should find that their device is responsive in some way, that means, they know what it is doing and maybe can record the next message to another colleague even if another one is not yet played to the receiver. 


## Domain

Decide if you want to optimize the system for a specific domain, or if you want to make it work in several settings. You could for instance focus on healthcare, offshore workers, farmers, athletes, just to name a few. This is a good point where your can distinguish your setup from that of others.


## Example Features

* Send short voice messages
* Avoid collisions if several messages arrive at the same time
* Replay for noisy environments
* Transcript (Speech to text)
* Detection of status, and handling of incoming messages accordingly
* Detection of network bandwidth, resubmissions


## Implementation


You should have a working demonstrator or prototype that shows some or most of the functionality you planned. 

Some more advanced functions are the following:

* Voice activation: Detection of activation words, followed by a detection of the recipient of a message, and detection when the message is complete. 

* Speech-to-text: Creation of a written form of the message, so the receiver could receive them as text instead, wither to save bandwidth on the receiver side or in noisy environments, or as accessibility feature.

* Text-to-speech: One could think of functionality where a message is transmitted as text and should be synthesized into speech for the receive to listen. 

The thing is: All of these functions are probably helpful, and we/you may implement some of them. But for the overall system design, we could replace some of these functions by code that imitates them. 
This is especially true when we assume that these functions are achieved by independent system components.
Then we can, for instance, replace a voice activation module with a module that imitates the voice activation, for instance with a graphical user interface, but has the same interface.  

The main part of your implementation must be in Python, and you need to implement some components using the state machine framework STMPY. This is to ensure that you can apply the learning material in the course. 




## Devices

There are several options for hardware to run the demo:

* Your laptop
* A Raspberry Pi
* A BBC Microbit

Here we haven't yet sorted out all the details and practicalities. 
One robust solution and maybe programming-wise the simplest would be to just use your own computers.

