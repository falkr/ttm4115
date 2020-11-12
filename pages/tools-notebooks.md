# Jupyter Notebooks


## Install JupyterLab

Follow the instructions on this page to [install Jupyter](https://jupyter.org/install).

* I recommend the **installation via pip**, since it usually gives you better control over your Python interpreter.


## Running Notebooks

* Details are [explained here](https://jupyter.readthedocs.io/en/latest/running.html#running)
* Usually, typing `jupyter lab` on your terminal is enough.
* A browser opens, by default to `http://localhost:8888`
* Navigate with the integrated file browser to the notebook you want to open, for example the ones you download form this course.

I recommend that you get used to lab and notebooks and routined at using them. They are super useful for all kinds of stuff, and I am using them daily. 


## Binder

If you don't manage to install Jupyter notebooks and run them, you can also try to use the following website that lets you use a notebook online with noetbooks you downloaded from a Git repository. 

[https://mybinder.org](https://mybinder.org)




# Troubleshooting



Find out which Python interpreter your notebook is using, create a cell with the following code and run it:

```
import sys
sys.executable
```


