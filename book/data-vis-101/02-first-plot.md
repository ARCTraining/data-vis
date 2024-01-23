# Building your first plot

Before we delve a little deeper into some of the concepts we introduced in the previous section with regards to what makes a graphic "good", let's lay the foundations and build our first plot. You need a draft to start improving on it!

In this course, we are going to be using a cloud-based development environment, so you don't have to install anything locally on your machine.

In this session, we are going to work step-by-step through building a basic plot. The full self-contained example script is given at the end of this page. 

```{admonition} Tip
:class: tip

It's a good idea to type the example code out in your notebook as opposed to copying and pasting. This will help you get used to the syntax and will allow you to improve your skills more rapidly.

```

## Introduction to the tools we are using

For this course, we are going to be using a particular tool for interacting with Python called a "Notebook". You may have heard of the Jupyter Notebook before: this is a document format that includes snippets of formatted text, embedded executable/runnable code, and the output of said code (for example, plots/figures). We are going to be using an online version of Jupyter Notebooks hosted by Google, called [Google Colaboratory](https://colab.google/); the free version provides plenty compute power for this tutorial.

|![image](figs/intro_to_colab.gif) | 
|:-:| 
| Click "New Notebook" to create a fresh file. *Alt text: gif of Google Colab's landing page, showing the "New Notebook" button being clicked.* |

Open up a new notebook for this session: click "New Notebook", then give the new file a sensible name. In a Python Notebook, you can create two different types of cells: a text cell, which can contain markdown-formatted text, and code cells, where you put Python code and can run it.

|![image](figs/intro_to_colab2.gif) | 
|:-:| 
| Hover the cursor over the bottom edge of the cell to show the options for a new text cell or code cell. *Alt text: gif of Google Colab's new notebook page, showing the new text cell and new code cell menu.* |

Try out the classic first program, "Hello World" from the first code cell, and click the run cell button to the left of the cell, or use the keyboard shortcut Ctrl + Enter:

```
print("Hello World!")
```

The first cell may take a while to run as Colab connects to the runtime, but shortly it should output `Hello World!` below your first code cell.

### Some useful keyboard shortcuts

| Action | Shortcut |
| :--- | :--- |
| Create new code cell | Ctrl + M B |
| Execute code cell | Shift + Enter |

## Refresher on the Python ecosystem

One of the pre-requisites for this course is some basic Python experience, but don't worry if you've forgotten how things work. For this course, we will be *importing* a variety of different libraries. Do this in the first cell of your notebook:

```
import matplotlib.pyplot
import numpy
```

When we use a *function* from one of these libraries, we need to prefix it with the module name, for example `numpy.loadtxt()`. 
In this course, we will be using some common shortened names/aliases for libraries, that saves us typing out the full name everytime we use them. You can replace the above code snippet with this:

```
import matplotlib.pyplot as plt
import numpy as np
```

The example `numpy.loadtxt()` above would now be instead written `np.loadtxt()`.

## Create some example data

In the next section of this course, we will run through how to load real data in in a variety of different ways. For this initial example, we are going to quickly generate some example data. Let's assume we want to create a **scatterplot** with 50 pairs of (x, y) data. Let's write some code that will generate 50 random numbers between zero and one.

```
# Create random x and y data

x = np.random.rand(50)
y = np.random.rand(50)
```

```{admonition} Tip
:class: tip

You can add comments to your code using the \# symbol; this text is skipped over when you tell the code to run; it is just for you or anyone else who reads your code to better understand what you are doing.

```

You can take a closer look at what this has produced by executing a cell that only contains `x` or `y`, or `print(x)`, `print(y)` (what is the difference between `x` and `print(x)` in terms of output?).


## How do I initialise a basic figure?

So you have your data and you want to build a scatterplot to see if there's any relationship between x and y. 

To create a plot in Python, we will always follow a few key steps.

First, we initialise the figure and the axes. The `figure` object can be thought of as the page you draw your plot onto. The `ax` object is the box drawn by the x and y axes, the "panel" your plot will be drawn in.

```
# Create a figure and axes objects

fig, ax = plt.subplots()
```

If you run this code, you should get an empty figure that looks something like this:

|![image](figs/empty_fig.png) | 
|:-:| 
| Empty axes without any data plotted. *Alt text: white rectangle area surrounded by x and y axes, with labels from 0-1 on both. No data points are plotted.* |

## How do I plot my data?

## How do I save this figure to my machine?

## What next...