# Jupyter Notebooks Introducing STMPY

To introduce STMPY you step by step and while executing code, we created a series of Python notebooks. 
You have two possibilities to run them


### Alternative 1: Install Notebooks on Your Computer

In this solution, you run Jupyter on your own computer. 

* Install Jupyter Lab on your computer, following [these instructions](tools-notebooks.html).
* Install the STMPY library:

```bash
python3 -m pip install --upgrade stmpy
```

We also need our own widgets in the notebooks, so run the following two commands:

```bash
python3 -m pip install ipywidgets
jupyter nbextension enable --py widgetsnbextension
```

* Visit the Github repository [https://github.com/falkr/stmpy-notebooks](https://github.com/falkr/stmpy-notebooks). 
    * You can pull the repository via Git, or 
    * Download directly the contents [as a ZIP file, using this link](https://github.com/falkr/stmpy-notebooks/archive/master.zip).


### Alternative 2: Use Binder

Binder runs notebooks online. 
Use this method if you have troubles running the notebooks on your own computer. 

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/falkr/stmpy-notebooks/HEAD)



## Run the Notebooks

The following notebooks will introduce you to STMPY step by step. 
At this time, you don't have to program anything on your own, just execute the cells and observe what's happening. So make sure you are not rushing through the cells too fast.

### State Machines in Python - Part 1

* Open the first notebook, stored in the file **State Machines in Python - Part 1.ipynb**
* In this notebook you learn all the basics of state machines in STMPY. 


### State Machines in Python - Part 2

* Work through the content of the notebook **State Machines in Python - Part 2.ipynb**
* You learn how we build very simple user interfaces in notebooks. We also use signals to send data from the user interface into the state machine.

### State Machines in Python - Part 3

* Work through the content of the notebook **State Machines in Python - Part 3.ipynb**
* You learn how you can also create states that have **entry** and **exit** actions.


### State Machines in Python - Part 4

* Work through the content of the notebook **State Machines in Python - Part 4.ipynb**
* You learn how to support decisions in state machines using **compound transitions.**