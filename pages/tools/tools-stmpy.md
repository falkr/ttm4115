# STMPY - State Machines in Python

The example implementations in this course are based on state machines in Python. For that, we use a library called STMPY. I've built it for this course and education purposes, so you have code that is (reasonably) easy to understand, low in complexity and easily accessible. 

STMPY is open source and free software. You are free to use it in your own projects. Contributions are welcome. 

Useful links:

* [STMPY Documentation](https://falkr.github.io/stmpy/)
* [STMPY API Documentation](https://falkr.github.io/stmpy/stmpy/)
* [Source Code on Github](https://github.com/falkr/stmpy)
* [Jupyter Notebooks with Examples](https://github.com/falkr/stmpy-notebooks)


## STMPY Example Notebooks

The [Jupyter Notebooks with Examples](https://github.com/falkr/stmpy-notebooks) contain some more advanced topics that you can study to consolidate and expand your knowledge on state machines:

* **Buffered Text To Speech:** We build a state machine that controls a text-to-speech synthesis. This is interesting also in general since you learn about do-activities which let us execute long-running operations. We also use deferred events.
* **Passing Data to Actions:** An example how actions (functions in Python) can have input data.
* **Polling with Two State Machines:** Here we create two state machines, one that is constantly polling the value of a sensor, and then notifying another state machine. It illustrates how one state machine can take care of some behavior (here constantly checking a sensor) and communicate with another state machine.
* **Audio Recording and Playback:** This is a more specific example on how to record and playback audio, and have a state machine for control of this.




## STMPY Components

Have a look at the [STMPY Components repository](https://github.com/falkr/stmpy-components). It provides examples how to make a component that contains state machines and that communicates via MQTT and JSON. 

<!--- * [Timer Manager Source Code](https://github.com/falkr/stmpy-components/docs/TimerManager.m.html) --->
* [Timer Manager Source Code](https://falkr.github.io/stmpy-components/TimerManager.py)
