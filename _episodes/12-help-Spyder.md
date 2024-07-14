---
title: "Loading a project"
teaching: 10
exercises: 10
questions:
- "How do I load a project?"
- "How well can you read/understand simple code blocks?"
objectives:
- "Become comfortable with loading projects and navigating their structure"
- "Become able to run code"
- "Become able to install library dependancies"
keypoints:
- "Inheriting projects is common, but they will not always come in this format"
- "Being able to read, understand, and run code that you did not write is not trivial."
---

## Important note
At this point, we are not trying to fully understand the code examples that follow. We are going to use them as a starting point to provide context for the material we learn today. If you are completely new to Python, it is not unexpected for this to feel and look intimidating but we want to provide some small examples that indicate how much can be achieved with only a few lines of code.   

## How do I load a project?

Download [this zip file](../fig/AISummerSchool.zip). Extract it to a sensible place. Go to Spyder and select **'projects'** > **'open projects'** and select the folder you just extracted.

{% include figure.html max-width="100%" file="/fig/project.png" 
alt="Spyder project pane" caption="Figure: Spyder layout once you have opened the project" %}

### What is this project?

This project includes **three** types of data (*tabular, images,* and *text*). It also features three simple, naïve code snippets that perform mildly interesting tasks. These examples are designed to be readable and straightforward, serving more as teaching tools than examples of best practice. Over the two days, you can modify these examples to make them more efficient and practical. If you are more confident with Python, you may want to experiment with all three examples; if not, you might prefer to concentrate on just one. We will use all three examples throughout the two days to illustrate key learning points. 

### Let's explore

Start with '**textexample.py**'. You can run this code by pressing the green play button that we saw in the previous session. If all goes well, you should see an output:

```
Top 10 words by occurance:
[('the', 72), ('to', 27), ('was', 16), ('in', 14), ('and', 14), ('of', 13), ('a', 13), ('that', 12), ('his', 10), ('plant', 10)]
```
{: .output}

Based on the output and the accompanying description/notes, we can make an educated guess about what is happening here. Python is relatively readable compared to other programming languages, so even with little to no experience, you should be able to understand the flow of the code.

Let’s move on to **'imageexample.py'**. When you try to run this code in the same way as the previous one, you are most likely to receive an error.

```
Traceback (most recent call last):

  File ~\anaconda3\envs\into_to_python\Lib\site-packages\spyder_kernels\py3compat.py:356 in compat_exec
    exec(code, globals, locals)

  File c:\users\james\.spyder-py3\temp.py:10
    import cv2

ModuleNotFoundError: No module named 'cv2'
```
{: .output}

This is a common problem when inheriting code from someone else, especially if you are not familiar with coding. The error indicates that the library we are trying to import cannot be found.

>**Context of libraries**
> We don’t want to constantly reinvent the wheel. Others have already created code that performs various useful tasks, and we don't want to waste time duplicating this work from scratch. Instead, developers have created libraries containing this code, which we can import into our projects and use.

**To fix**

We need to install the packages into our environment. We will spend more time exploring environments and packages later, but for now, all you need to know is that the package must be installed in any environment where you want to use it.

>## Important
>* **Spyder and Anaconda specific**  
>These instructions are for using Spyder with Anaconda Navigator, which, from our experience, causes the fewest errors and conflicts on people's machines. If you are using your own setup, this method may not work as intended, so you will need to install packages in the way you normally would or seek assistance from a demonstrator. 
{: .callout}


```
pip install opencv-python
```
{: .language-python}

Type this command into the console and give Spyder time to find and install the package. If the installation is successful, you should now be able to run the code. When it runs you should be presented with an image of some jute leaves. Pressing any button will replace the jute leaves with an image now showing only the lines that have detected in the image.

{% include figure.html max-width="100%" file="/fig/leaves.png" 
alt="Leaves and the lines in the leaves image" caption="Figure: The two outputs you should see when running imageexample.py" %}


### You will need to press any key to close each image after it displays.

It may seem like we are achieving a lot with very few lines of code. This is because the heavy lifting is done by cv2.Canny, a function imported from OpenCV. We will explore functions in more detail later, but for now, you can think of it as we are using code that is stored elsewhere.


## Last example

From the Script pane bar select 'tabularexample.py'.

> ## Question: Can you get this code to run?
> You may need 'pip install pandas' and 'pip install matplotlib'.
{: .challenge }

Once you have installed the libraries, you should be able to run this example. If you check the Plots Pane, you should see a plot illustrating the relationship between petal length and petal width in the dataset.

>## Tip
>* **We can make plotting display in a new window**  
> From the Menu bar select '*tools*' > '*preferences*' >'*IPython console*' > '*Graphics*' > change Backend to '*Automatic*' press 'Apply'.
{: .callout}

{% include figure.html max-width="100%" file="/fig/inline.png" 
alt="Spyder iconsole pane" caption="Figure: How to change plots to an external pane" %}  
  
Run the code again (you may need to restart Spyder), and the plot should now generate in a new window that you may find easier to manipulate/view.





