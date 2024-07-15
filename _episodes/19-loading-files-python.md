---
title: "Re-visiting 'textexample.py'"
teaching: 10
exercises: 5
questions:
- "How does the textexample.py file work?"
objectives:
- "Can understand what each line in achieving."
keypoints:
- "Different ways to deal with inputs based on type, size, and complexity"
- "Different data structures for different tasks"
---

### What is going on? (line by line)

```
with open( "data/bed_time_stories/2. Who is the thief.txt", encoding='utf-8') as story:
```
{: .language-python}

Keyword: **with**
In Python this is used extensively for file handling.

Function: **open**
We are going to open a file. We provide the file path and the encoding.

Keyword: **as**
We need to name the file we are opening so it can be refered to in the code.

Variable name: **story**
We choose this variable name for clarity (think back to variable naming).

```
for line in story:
            
        words = line.split()
```
{: .language-python}

Keyword: **for**
We know how for loops work now. We know we are going to iterate over every line in the story. We are then going to call a method on line to **split()** it into words.
{: .callout}

```
        for word in words:
    
            #if we have seen the word before incriment the occurances
            if word in word_dict:
                word_dict[word] += 1
            
            #if we havent, put the word in and set the count to 1
            else:
                word_dict[word] = 1
```
{: .language-python}
 
Keyword: **if**

We now know if the condition resolves as True we will execute the code underneath if, **else** we will execute the code underneath else. If the word is in the dictionary, incriment the occurances, otherwise, put the word in and set the count to 1.

```
sorted_by_occurance = sorted(word_dict.items(), key = lambda item: item[1], reverse = True)
#print the top 10 words and their number of occurances
print("Top 10 words by occurance:")
print(sorted_by_occurance[:10])
```
{: .language-python}

Finally, we sort the items in the dictionary that is provided by **word_dict.items()**. We use the lambda to select the value. We put reverse as True because the default is sorting low to high. Then we print the results.

> ## Do you have any questions?
> Take some time to explore, and understand this example. What questions do you need to ask to fully understand? 
{: .challenge}



