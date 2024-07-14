---
title: "Re-visiting 'textexample.py'"
teaching: 5
exercises: 5
questions:
- "How do I load my own data into Spyder?"
objectives:
- "Can load data files into Spyder."
keypoints:
- "Loading in the data is just the first step"
---

### Text example


```
with open( "data/bed_time_stories/2. Who is the thief.txt", encoding='utf-8') as story:
```
{: .language-python}


```
with open( "data/bed_time_stories/2. Who is the thief.txt", encoding='utf-8') as story:
```
{: .language-python}

Keyword: **with**
In Python this is used extensively for file handling.

Function: **open**
We are going to open a file. We provide the file path and the encoding.

Keyword: **as**
We need to name our file so we can refer to it.

Variable name: **story**
We chose this variable name, we will talk about variables and their naming in length later. For now all you need to know is that we choose this name and anytime in the code we use this name we are talking about the file we just opened.

