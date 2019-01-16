---
status: draft
---

# Timer Module for a Voice Assistant

Your task is to build the module that allows a voice assistant to maintain timers. The timers should have a name, and it should be possible for a user to start as many timers as they want. Currently, Alexa can have these named timers, while Siri cannot. This means, a user should be able to say:

> "Hey Assistant*, please start a 10-minute spaghetti timer."

During this timer is active, the user can start another timer:

> "Hey Assistant*, start a 2-minute green tea timer."

These timers are independent of each other. Once they expire, the assistant says:

> "Your green tea timer is ready!"
 
And then later:

> "Your spaghetti timer is ready!"


https://youtu.be/VqAPibRlTvo


The part of the system you are concerned with looks as follows:

<div class="mxgraph" style="max-width:100%;border:1px solid transparent;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;lightbox&quot;:false,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;url&quot;:&quot;https://drive.google.com/uc?id=1UjAIbZzzBUW5G_qATLOtiieN3NRl3OTS&amp;export=download&quot;}"></div>
<script type="text/javascript" src="https://www.draw.io/embed2.js?&fetch=https%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1UjAIbZzzBUW5G_qATLOtiieN3NRl3OTS%26export%3Ddownload"></script>


* The voice command detection is responsible for listening for the activation command ("Hey Assistant"), and the subsequent interpretation of the command. It uses some support from the data center, which we are not concerned with here. 

* The text-to-speech engine runs locally. It receives strings that are then transformed into speech. Each act of speech is called an "utterance". It also pays attention that several utterances are queued up, i.e., when the module receives several utterances that would overlap, it plays them nicely one after the other.

You should design the timer manager in the middle. It receives commands from the voice command detection, should maintain the control over the necessary timers, and produce commands for the text-to-speech engine.

From the voice command detection, you may receive the following commands:

* **Starting a new timer:** The command is called *timer_start* and includes the *name* of the timer (string) and the *duration* already converted into seconds (as int).  
* **Stopping a timer:** The command is called *timer_stop* and includes the *name* of the timer (string) that should be stopped.
* **Status:** The command is called *timer_status*. The user can either ask for a specific timer, then the *name* is set. If the name is not set, the device should present a list of all currently active timers.

The text-to-speech just accepts a command that contains a sentence in English. For the timers, you will probably produce the following utterances:

* "Your spaghetti timer is ready!"
* "You have 30 seconds left on the spaghetti timer."
* "Your have 2 active timers, spaghetti and green tea." 



## Hint 1: MQTT 

* Have a look at the MQTT Notebook to get all necessary information on how to publish and subscribe using MQTT.

## Hint 2: Serialization

* Have a look at the Serialization with JSON Notebook, that tells you how to serialize structured data, like the commands above, into strings that can easily be sent for instance via MQTT.

## Hint 3: Component Structure

* Once challenge of the system is that it needs to maintain control over many (in principle and unlimited number of) timers at the same time. All of the timers have some stateful behavior, because they can expire at any time. You could create a system that continuously runs over a list of timers, determines which of them expired and then schedules the necessary test-to-speech utterances. However, this is a job that can be done by a set of state machines. **You should therefore create a new state machine instance for every timer that gets started.**


* update STMPY to version 0.5.1. This latest version adds a method `get_timer(name)` in the Machine class so you can check the current state of a timer with a given name. The method returns the time in seconds remaining for the timer, or None if the timer is currently not active.

* Install the application **MQTT.fx** from [here](http://mqttfx.jensd.de). With this application, you can send and receive MQTT messages. You can use it to simulate the functions of the text-to-speech engine and the voice command detection.

* Use the template TimerManager.py form the repository as optional starting point. https://github.com/falkr/stmpy-notebooks/blob/master/TimerManager.py