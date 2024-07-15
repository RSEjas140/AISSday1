---
title: "Re-visit 'tabularexample.py'"
teaching: 10
exercises: 5
questions:
- "How does the tabularexample.py file work?"
objectives:
- "You can understand what each line in achieving."
keypoints:
- "Image can be represented as numeric values"
- "Don't reinvent the wheel"
- "Use functions anytime you have highly repetative code"
---

### What is going on? (line by line)

```
#read data from csv
iris = pd.read_csv("data/iris.csv")
```
{: .language-python}

* function: **read_csv**  
We use Pandas to read in a csv given a file path.


```
print(iris.head())
```
{: .language-python}

* Function: **head()**

Displays top 5 lines from the dataframe. We are going to spend a lot of tomorrow looking at Pandas and dataframes.

```
colour_map = {'Setosa': 'red', 'Versicolor': 'green', 'Virginica': 'blue'}
#create a list of colours to use for scatter plot
colours = iris['variety'].map(colour_map)
```
{: .language-python}
 
We create a dictionary(colour_map), with key(variaty) and value(colour). This is so we can map the variety to our plotted data and generate a list(colours) based on the values in the 'variety' column in the dataset.

```
iris.plot.scatter('petal.length','petal.width', c = colours)
```
{: .language-python}

* Function: **.plot.scatter(x,y)**  
We provide the column names for the data we want to display and then the colours related to those data points. 


> ## Do you have any questions?
> Take some time to explore, and understand this example. You may want to look up the cv2 functions to discover what other parameters they take. Are there any questions you need to ask to fully understand? 
{: .challenge}


