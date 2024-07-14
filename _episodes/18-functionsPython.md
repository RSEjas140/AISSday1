---
title: "Functions"
teaching: 25
exercises: 15
questions:
- "How do I make my own functions?"
- "Why would I want to make my own functions?" 
objectives:
- "Understand function structure"
- "Confident declaring custom functions"
keypoints:
- "Functions can help reduce redundancy and increase reusability in your code"
---

## Exploring functions

So far, we have just been using functions without exploring what they are doing. For example, you type `math.sqrt()` and place your value (argument/parameters) into the function, some magic happens, and it returns an output. We will now start to explore the structure of functions and how we can create our own.  

## Function Structure

```python
def function_name(parameter1, parameter2, ...):
    """Description of the function."""
    # Function body
    return result
```

- **def**: Keyword to define a function.
- **function_name**: Name of the function.
- **(parameter1, parameter2, ...)**: Parameters (optional).
- **Description**: Brief function description for users (not used by Python).
- **return**: Keyword to return a value (optional).
- **result**: Value to be returned (optional).


## Features of functions

### Immutable vs Mutable
In Python, function arguments are 'passed by assignment'. This means that when you pass a variable to a function, you are passing a reference to the object that the variable refers to. A function can modify the passed object if the object is mutable (e.g., lists, dictionaries) and can not be modified if the object is immutable (e.g., integers, floats, strings).  

```python
def my_func(x):
    x = 10

a = 5

my_func(a)

print(a)
```

```
5
```
{: .output}


```python
def my_func(x):
    x.append(5)

my_list = [1,2,3,4]

my_func(my_list)

print(my_list)
```

```
[1,2,3,4,5]
```
{: .output}

### Lambda fuctions

Lambda functions in Python are small, anonymous functions defined with the **lambda** keyword. They are often used for short, simple functions that are not worth defining with a full def statement. 

Lambda syntax:
```python
lambda arguments: expression
```

Lambda example:

We have seen a lambda function in our 'textexample.py' which was 'lambda item: item\[1\]'. This was part of the sort function and what we were providing was the element to sort by. If given an item from the dictionary (item = key,value) return item[1], the value. This is because we wanted to sort by he value (in this case the number of occurances). 

### Default arguments

You will recieve an error if you do not provide the expected number of arguments to a function. However, default arguments in Python allow you to specify default values for one or more parameters of a function. If an argument for a parameter with a default value is not provided during the function call, the function uses the default value. It is important to know this for when you write your own functions but also if you are using libraries that you are aware there might be default values being used.

```python
def my_greeting_func(name, greeting = "hello"):
    # this is an example of f-string it is a more advanced but more efficient way to create and print a formatted string.
    print(f"{greeting}, {name}!")


my_greeting_func("Alice")

``` 

```
Hello, Alice!
```
{: .output}

## Creating a function

We can convert our previous calculation into a function. Open a new script file and type this in: 

```python
def celc_to_fahr(celc):
    fahr = celc * 9/5 + 32
    return fahr
```

Save this script as 'my_functions' and run it.

Now we can convert Celsius to Fahrenheit in the console by typing:

```
celc_to_fahr(14) 
```
{: .language-python}
```
57.2
```
{: .output}

Go back to to the script my_first_script. At the top of the script place this line:

```
import my_functions as mf
```
{: .language-python}

```
mf.celc_to_fahr(14) 
```
{: .language-python}

We can now run this function from my_first_script.

Wherever significant duplication exists in your code, it's advisable to create a function to replace it. This approach promotes code reusability, readability, and maintainability. If you have generalised functions that you use often in different scripts, it is good practice to store them in a script file. You can then import them into any project that you need them for. This reduces rewriting and editing code, and decreases the chance of introducing errors such as typos or calculation errors.
