Posted on 2018-05-23 | In [Course Notes](https://joannaoyzl.github.io/categories/Course-Notes/) | Visitors:

Datacamp course notes on basic calculation, variables and types, functions, and Numpy.  

## [](https://joannaoyzl.github.io/2018/05/23/Intro-to-Python/#Basic-Calculation "Basic Calculation")Basic Calculation

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br><span>7</span><br><span>8</span><br><span>9</span><br></pre></td><td><pre><span><span># Summation</span></span><br><span><span>2</span> + <span>3</span></span><br><span><span>'ab'</span>+<span>'cd'</span> <span>#this simply paste 'cd' and 'ab' together</span></span><br><span></span><br><span><span># Exponentiation</span></span><br><span><span>4</span> ** <span>2</span></span><br><span></span><br><span><span># Modulo</span></span><br><span><span>18</span> % <span>7</span></span><br></pre></td></tr></tbody></table>

## [](https://joannaoyzl.github.io/2018/05/23/Intro-to-Python/#Variable-amp-Types "Variable & Types")Variable & Types

### [](https://joannaoyzl.github.io/2018/05/23/Intro-to-Python/#Variable "Variable:")Variable:

-   Specific, case-sensitive name
-   Call up value through variable name
-   Can help to make your code reproducible

### [](https://joannaoyzl.github.io/2018/05/23/Intro-to-Python/#Type "Type:")Type:

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br></pre></td><td><pre><span><span># To know the type of a variable</span></span><br><span>type(variable)</span><br></pre></td></tr></tbody></table>

1.  Float, a value with both fractional and integer part
2.  Int
3.  Str, text. Can use both double and single quotes.
4.  Bool, 0 & 1/False & True **True/False is case sensitive here**

_Note: Different types have different behavior_

To paste strings and floats together, we can simply put:  

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br></pre></td><td><pre><span>print(<span>"I started with $"</span> + str(savings) + <span>" and now have $"</span> + str(result) + <span>". Awesome!"</span>)</span><br><span></span><br><span>print(<span>"I said "</span> + (<span>"Hey "</span> * <span>2</span>) + <span>"Hey!"</span>)</span><br></pre></td></tr></tbody></table>

Other conversion functions: `int()`,`float()`,`bool()`

5.  List  
    **Characteristics**

-   Name a collection of values. `d = [a,b,c]`
-   Can contain any type and different types
-   List of lists: `d2 = [[a,1],[b,2],[c,3]]`

**Subsetting lists**  
zero-based indexing: start from 0

-   `x[0]`: returns the first element
-   `x[-1]`: returns the last element
-   `x[-2]`: returns the last but one element
-   `x[3:5]`: returns the fourth and fifth element. _The element represented by index 5 is not selected, so this slicing is like \[start:end) mathemetically_
-   `x[:4]`: returns all the element from the start to the **fourth**
-   `x[5:]`: returns all the element from the **sixth** element to the last one

**List Manipulation**

-   Replaced the indexed part of the list with desired values
    
    <table><tbody><tr><td><pre><span>1</span><br></pre></td><td><pre><span>x[<span>0</span>:<span>2</span>] = [a,b]</span><br></pre></td></tr></tbody></table>
    
-   Adding and removing elements
    
    <table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br></pre></td><td><pre><span><span># adding</span></span><br><span>x = x + [a,b]</span><br><span></span><br><span><span># removing</span></span><br><span><span>del</span>(x[<span>2</span>])</span><br></pre></td></tr></tbody></table>
    

_Important Note: when you create a new list, what actually happens is that you store a list into the computer memory, and store the “address” of the list to the variable. This means that the variable actually does not contain all the list elements, but rather contains a reference to the list elements. This difference is especially important when you try to copy the list:_  

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br></pre></td><td><pre><span>x = [<span>'a'</span>, <span>'b'</span>, <span>'c'</span>]</span><br><span>y = x</span><br><span>y[<span>1</span>] = <span>'z'</span></span><br></pre></td></tr></tbody></table>

Now if you print `y`, you will see the following output: `['a', 'z', 'c']`, while interestingly, the element in `x` is also changed into `['a', 'z', 'c']`. That is because when you copy `x` to `y` with an equal sign, you copied the reference to `y`, not the list elements themselves. Therefore, when you are updating an element in the list, which was stored in the computer memory, both `x` and `y`, whose reference point to this list, will return changed outcome.

If you want to create a list `y` with a new list of elements but same values as `x`, you should use `y = list(x)` or `y = x[:]` to select all the elements explicitly. Now when you update the elements in `y`, `x` will not change accordingly.

## [](https://joannaoyzl.github.io/2018/05/23/Intro-to-Python/#Functions "Functions")Functions

`help(function)` can help you understand the arguments. If the argument is in square brackets, then it is an optional one.

### [](https://joannaoyzl.github.io/2018/05/23/Intro-to-Python/#Objects-and-Methods "Objects and Methods")Objects and Methods

All kinds of values or data structures, like strings, floats, lists, etc., are all python objects, and methods are functions that belongs to objects. Methods may behave differently for different objects.  
To use a method, an example with list are as follows: `x.index(a)`, `x.count(a)`

Useful tips and functions:

1.  To place two commands in the same line: `command1; command2`
2.  `max()`, `min()`
3.  `round(x, digits)` #default to 2
4.  `len(x)`: length of a variable
5.  `sorted(x, reverse = TRUE/FALSE, key = column)`: sort the variable in ascending or descending order. _For a list, reverse() should be used instead_
6.  `capitalize()` or `upper()`: capitalize all the letters in a string
7.  `replace('a', 'b')`: replace ‘a’ with ‘b’
8.  `append()`: append a value to the end of the list
9.  `count('a')`: count the number of appearance of letter ‘a’ in the string

## [](https://joannaoyzl.github.io/2018/05/23/Intro-to-Python/#Packages "Packages")Packages

Conveniently install packages with pip in terminal after downloading the get-pip.py  

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br></pre></td><td><pre><span>python3 get-pip.py</span><br><span>pip3 install numpy</span><br></pre></td></tr></tbody></table>

### [](https://joannaoyzl.github.io/2018/05/23/Intro-to-Python/#Import-the-package "Import the package")Import the package

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br><span>7</span><br></pre></td><td><pre><span><span>import</span> numpy <span>as</span> np</span><br><span>np.array([<span>1</span>, <span>2</span>, <span>3</span>])</span><br><span></span><br><span><span>#if you only need one function from the package</span></span><br><span><span>from</span> numpy <span>import</span> array</span><br><span>array([<span>1</span>, <span>2</span>, <span>3</span>])</span><br><span><span>#this way, the reader of your code may not know explicitly that you are calling the fucntion from numpy. Therefore the previous method is usually more preferable.</span></span><br></pre></td></tr></tbody></table>

## [](https://joannaoyzl.github.io/2018/05/23/Intro-to-Python/#Numpy "Numpy")Numpy

-   Great for vector arithmetic
-   Support element-wise calculation on lists
-   Fast and easy  
    `np.array(list)` can easily convert a list into a numpy array.
-   Remarks:

1.  numpy arrays only contain one type. If the array contains different types, some of the types will be coerced to produce a homogeneous list.
2.  adding arrays together will perform element-wise calculation, while adding lists together simply paste the lists together without calculation.  
    `np.array([True, 1, 2])` will become `array([1, 1, 2])`

### [](https://joannaoyzl.github.io/2018/05/23/Intro-to-Python/#Subsetting "Subsetting")Subsetting

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br></pre></td><td><pre><span>x[<span>1</span>]</span><br><span>x[x&gt;<span>1</span>]</span><br></pre></td></tr></tbody></table>

### [](https://joannaoyzl.github.io/2018/05/23/Intro-to-Python/#2D-Numpy-Arrays "2D Numpy Arrays")2D Numpy Arrays

-   ndarray = N-dimensional array
-   needs homogeneous type
    
    <table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br></pre></td><td><pre><span>np_2d = np.array([[<span>1.73</span>, <span>1.68</span>, <span>1.71</span>],[<span>65.4</span>, <span>59.2</span>, <span>63.6</span>]])</span><br><span>np_2d.shape <span>#returns the dimension </span></span><br><span>np_2d[<span>0</span>] <span>#selects the first row</span></span><br><span>np_2d[<span>0</span>][<span>2</span>] <span>#selects the third element in the first row</span></span><br><span>np_2d[<span>0</span>, <span>2</span>] <span>#selets the element at row 1 column 3</span></span><br><span>np_2d[:, <span>1</span>:<span>3</span>] <span>#selects column 2 and 3 (remember the 3 index is not included here)</span></span><br></pre></td></tr></tbody></table>
    

### [](https://joannaoyzl.github.io/2018/05/23/Intro-to-Python/#Basic-Statistics "Basic Statistics")Basic Statistics

-   Much faster

1.  `np.mean()`, `np.median()`, `np.corrcoef(a, b)`, `np.std()`
2.  `sum()`, `sort()`

To generate data: `np.random.normal(mean, sd, number)`

To paste columns together: `np.column_stack((a,b))`