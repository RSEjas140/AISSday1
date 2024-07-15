---
title: "Re-visit 'imageexample.py'"
teaching: 10
exercises: 5
questions:
- "How does the imageexample.py file work?"
objectives:
- "You can understand what each line in achieving."
keypoints:
- "Images can be represented as numeric values"
- "Don't reinvent the wheel"
- "Use functions anytime you have highly repetative code"
---

### What is going on? (line by line)

```
# my function for displaying images
def show_image(img):
    """ docstring
    Pass in an image and it will be displayed until you press any key

    Parameters
    ----------
    img : Array
        Image we want to display.

    Returns
    -------
    None.

    """    
    #show image
    cv2.imshow('image', img)
    #wait until a key is pressed
    cv2.waitKey(0)
    #close image
    cv2.destroyAllWindows()
```
{: .language-python}

* Keyword: **def**  
We know now that we are **def**ining a function. We will use this function to display the images we load in.
The following lines among the """ are docstrings. They document how the function works and are really important to help future-you and other collaborators understand your code.

```
image = cv2.imread("data/crop_images/jute/jute018a.jpeg")
```
{: .language-python}

* Function: **imread()**

Read an image in based on a given file path.

```
grey_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```
{: .language-python}
 
* Function: **cvtColor**

Convert the image into greyscale.

```
edges = cv2.Canny(grey_image, 100, 200)
```
{: .language-python}

* Function: **Canny**  
Use canny edge detection to identify edges.


> ## Do you have any questions?
> Take some time to explore, and understand this example. You may want to look up the cv2 functions to discover what other parameters they take. Are there any questions you need to ask to fully understand? 
{: .challenge}
