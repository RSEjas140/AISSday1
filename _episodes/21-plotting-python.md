---
title: "Re-visit 'tabularexample.py'"
teaching: 10
exercises: 5
questions:
- "How does the tabularexample.py file work?"
objectives:
- "You can understand what each line in achieving."
keypoints:
- "Tabular data can be massive; pandas DataFrames are a great way to deal with this data."
- "Plotting is a really useful analysis tool as well as a way of producing clean-looking figures."
---

### What is going on? (line by line)

```
#read data from csv
iris = pd.read_csv("data/iris.csv")
```
{: .language-python}

* function: **read_csv**  
We are using pandas to read in a CSV file given a file path. There are a huge number of different files with custom delimiters that pandas can read.

```
print(iris.head())
```
{: .language-python}

* Function: **head()**

This function displays the top 5 lines from the DataFrame. We are going to spend a lot of time tomorrow exploring DataFrames, learning how to manipulate them, and how to display the data they contain.

```
colour_map = {'Setosa': 'red', 'Versicolor': 'green', 'Virginica': 'blue'}
#create a list of colours to use for scatter plot
colours = iris['variety'].map(colour_map)
```
{: .language-python}
 
We created a dictionary (colour_map), with keys (variety) and values (colour). This allows us to map the variety to our plotted data and generate a list (colours) based on the values in the 'variety' column in the dataset.
```
iris.plot.scatter('petal.length','petal.width', c = colours)
```
{: .language-python}

* Function: **.plot.scatter(x,y)**  
We provide the column names for the data we want to display, along with the colours we want the data displayed as. Plot.scatter() then generates a scatter plot for that information.   


> ## Do you have any questions?
> Take some time to explore, and understand this example. You may want to look up the cv2 functions to discover what other parameters they take. Are there any questions you need to ask to fully understand? 
{: .challenge}


