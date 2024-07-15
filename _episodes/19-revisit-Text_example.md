---
title: "Re-visit 'textexample.py'"
teaching: 10
exercises: 5
questions:
- "How does the textexample.py file work?"
objectives:
- "You can understand what each line in achieving."
keypoints:
- "Different ways to deal with text inputs based on type, size, and complexity"
- "Different data structures for different tasks"
---

### What is going on? (line by line)

```
with open( "data/bed_time_stories/2. Who is the thief.txt", encoding='utf-8') as story:
```
{: .language-python}

* Keyword: **with**  
In Python this is used extensively for file handling.

* Function: **open**  
We are going to open a file. We provide the file path and the encoding.

* Keyword: **as**  
We need to name the file we are opening so it can be referred to in the code.

* Variable name: **story**  
We choose this variable name for clarity (think back to variable naming).

```
for line in story:
            
        words = line.split()
```
{: .language-python}

* Keyword: **for**
We know how for loops work now. We are going to iterate over every line in the story. We will then call a method on 'line' to **split()** it into words.

```
        for word in words:
    
            #if we have seen the word before increment the occurances
            if word in word_dict:
                word_dict[word] += 1
            
            #if we havent, put the word in and set the count to 1
            else:
                word_dict[word] = 1
```
{: .language-python}
 
* Keyword: **if**

We now know that if the condition resolves as True, we will execute the code underneath if; otherwise, we will execute the code underneath else. If the word is in the dictionary, increment the occurrences; otherwise, add the word to the dictionary and set the count to 1.

```
sorted_by_occurance = sorted(word_dict.items(), key = lambda item: item[1], reverse = True)
#print the top 10 words and their number of occurances
print("Top 10 words by occurance:")
print(sorted_by_occurance[:10])
```
{: .language-python}

* Keyword: **sorted**  
The in-built Python sorting function returns a new sorted list containing all items from an iterable. This sorts the items in the dictionary (provided by word_dict.items()). We use the lambda to select the value rather than the key. We set reverse to True because the default for sorted is ascending order (low to high). Then we print the resulting list at the indices we want.

> ## Do you have any questions?
> Take some time to explore, and understand this example. What questions do you need to ask to fully understand it? 
{: .challenge}



