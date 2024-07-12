---
title: "Loading a project"
teaching: 10
exercises: 5
questions:
- "How do I load a project?"
objectives:
- "Comfortable with loading projects and navigating their structure"
keypoints:
- "Inheriting projects is common, they will not always come in this format"
---

## How do I load a project?

Download [this zip file](../fig/AISummerSchool.zip). Extract it to a sensible place. Go to Spyder and select **'projects'** > **'open projects'** and select the folder you just extracted.

{% include figure.html max-width="100%" file="/fig/project.png" 
alt="Spyder project pane" caption="Figure: Spyder layout once you have opened the project" %}

### What is this project?

This project includes **three** kinds of data (*tabular*, *images*, & *text*). It also includes three simple, nieve code snippits that do something mildly interesting. These examples are designed to be readable and straight-forward and serve as teaching tools more than examples of good practice. Throughout the two days you can modify these examples to make them more efficient and practical. If you are more confident with Python you may want to experiment will all three examples, if you are not you may want to concentrate on a single one. We will be using all three throughout the two days to illustrate learning points.   

### Let's explore

Start with '**textexample.py**'. We can run this code by pressing the green play button that we saw in the previous session. If all goes well you should see an output:

```
Top 10 words by occurance:
[('the', 72), ('to', 27), ('was', 16), ('in', 14), ('and', 14), ('of', 13), ('a', 13), ('that', 12), ('his', 10), ('plant', 10)]
```
{: .output}

Based on the output and the description/notes we can make an educated guess at what is going on here. Python is relatively readable as far as programming languages go, so even with little to no experience you should be able to understand the flow of what is going on.

Let's move on to '**imageexample.py**'. When you try to run this the same way you ran the previous code you most likely will recieve an error.

```
Traceback (most recent call last):

  File ~\anaconda3\envs\into_to_python\Lib\site-packages\spyder_kernels\py3compat.py:356 in compat_exec
    exec(code, globals, locals)

  File c:\users\james\.spyder-py3\temp.py:10
    import cv2

ModuleNotFoundError: No module named 'cv2'
```
{: .output}

This is a really common problem when you are inheriting code from someone and you are not familiar with coding. What this error is telling us is that the **library** we are trying to import can not be found.

>**Context of libraries**
> We do not want to be constantly re-inventing the wheel. People before us have created code that does all kinds of very useful things that we do not want to waste our time duplicating from scratch. Coders before us have created libraries of this code and we can import that into our projects and use it.

**To fix**

We need to install the packages into our environment, we will spend more time exploring environments and packages but for now all you need to know is that we need to install the package into any environment we want to use it in.

**NB** - These instructions are for use of Spyder with Annaconda Navigator and from our experience causes the least amount of error and conflicts on peoples machines. If you are using your own set-up this may not work as intended so you will have to install packages the way that you would normally or you will need to get a demonstrator to help you. 

```
pip install opencv-python
```
{: .language-python}

Type this command into the console and give Spyder time to find and install the package. If it has installed correctly you should now be able to run the code and you should be presented with an image of some leaves, if you press any button that image will be replaced by an image of just the lines detected in that image.

{% include figure.html max-width="100%" file="/fig/leaves.png" 
alt="Leaves and the lines in the leaves image" caption="Figure: The output you should get when running the imageexample.py" %}

Press any key and the second image will close.

It may seem like we are achieving a lot with very few lines of code. That is because all the heavy lifting is being done by *cv2.Canny*. This is a function we have imported from openCV. We will look at functions in more detail but for now you can just imaging that we are calling some other code stored elsewhere 





