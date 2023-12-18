---
type: nav
prev: ["Documentation", "index.html"]
---

# Installation

## Install Python

Install [Python 3.x](https://www.python.org).
Make sure that you let the installer add the Python command line tools to your path,
so that you can later execute the pip command and the other commands that Supermark comes with.

## Install Pandoc

Install [Pandoc](https://pandoc.org/installing.html). 

If you share a project with others, or run Supermark also as Github Action, try to install Pandoc version **2.12**.
This ensures that files are generated identically and do not cause unnecessary changes in version control. 

## Install Supermark

```bash
pip install supermark
```