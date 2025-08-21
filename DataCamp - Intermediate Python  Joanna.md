Posted on 2018-05-23 | In [Course Notes](https://joannaoyzl.github.io/categories/Course-Notes/) | Visitors:

Datacamp course notes on data visualization, dictionaries, pandas, logic, control flow and filtering and loops.  

## [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Data-Visualization "Data Visualization")Data Visualization

### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Matplotlib "Matplotlib")Matplotlib

##### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Line-graph "Line graph")Line graph

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br></pre></td><td><pre><span><span>import</span> matplotlib.pyplot <span>as</span> plt</span><br><span>year = [<span>1950</span>, <span>1970</span>, <span>1990</span>, <span>2010</span>]</span><br><span>pop = [<span>2.519</span>, <span>3.692</span>, <span>5.263</span>, <span>6.972</span>]</span><br><span>plt.plot(year, pop) <span>#(x, y)</span></span><br><span>plt.show()<span># before this step, you can add labels or other things to customize your plot.</span></span><br></pre></td></tr></tbody></table>

##### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Scatter-plot "Scatter plot")Scatter plot

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br></pre></td><td><pre><span><span>import</span> matplotlib.pyplot <span>as</span> plt</span><br><span>year = [<span>1950</span>, <span>1970</span>, <span>1990</span>, <span>2010</span>]</span><br><span>pop = [<span>2.519</span>, <span>3.692</span>, <span>5.263</span>, <span>6.972</span>]</span><br><span>plt.scatter(year, pop, s = pop, c = col, alpha = <span>0.8</span>) <span># s controls the size of the circle, c controls the color of the bubbles, alpha controls the opaqueness(0-1)</span></span><br><span>plt.xscale(<span>'log'</span>) <span># show x-axis on a logarithmic scale</span></span><br><span>plt.show()</span><br></pre></td></tr></tbody></table>

##### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Histogram "Histogram")Histogram

-   Explore dataset
-   Get idea about distribution
    
    <table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br></pre></td><td><pre><span><span>import</span> matplotlib.pyplot <span>as</span> plt</span><br><span><span># bins = 10 by default, the more the bins, the more detailed of the contour</span></span><br><span>plt.hist(values, bins = <span>3</span>)</span><br><span>plt.show()</span><br><span>plt.clf()<span># this cleans up the graph so that you can start fresh</span></span><br></pre></td></tr></tbody></table>
    

### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Customization "Customization")Customization

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br><span>7</span><br><span>8</span><br><span>9</span><br><span>10</span><br><span>11</span><br></pre></td><td><pre><span><span>import</span> matplotlib.pyplot <span>as</span> plt</span><br><span>year = [<span>1950</span>, <span>1970</span>, <span>1990</span>, <span>2010</span>]</span><br><span>pop = [<span>2.519</span>, <span>3.692</span>, <span>5.263</span>, <span>6.972</span>]</span><br><span>plt.plot(year, pop) <span>#(x, y)</span></span><br><span>plt.xlabel(<span>'Year'</span>)</span><br><span>plt.ylabel(<span>'Population'</span>)</span><br><span>plt.title(<span>'World Population Projections'</span>)</span><br><span>plt.yticks([<span>0</span>, <span>2</span>, <span>4</span>, <span>6</span>, <span>8</span>, <span>10</span>],[<span>'0'</span>, <span>'2B'</span>, <span>'4B'</span>, <span>'6B'</span>, <span>'8B'</span>, <span>'10B'</span>]) <span>#specify the intervales on y axis and also the number show</span></span><br><span>plt.text(<span>1550</span>, <span>71</span>, <span>'India'</span>) <span>#show text at a cetain (x,y)</span></span><br><span>plt.grid(<span>True</span>) <span>#show gridlines</span></span><br><span>plt.show()<span># before this step, you can add labels or other things to customize your plot.</span></span><br></pre></td></tr></tbody></table>

## [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Dictionaries "Dictionaries")Dictionaries

-   make it easier to connect two lists without using index as a bridge
-   syntax: `{key1:value1, key2:value2 ...}`. `dict_name[key]` will return the corresponding value
    
    <table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br><span>7</span><br><span>8</span><br><span>9</span><br><span>10</span><br><span>11</span><br><span>12</span><br><span>13</span><br><span>14</span><br></pre></td><td><pre><span>world = {<span>'a'</span>:<span>1</span>, <span>'b'</span>:<span>2</span>, <span>'c'</span>:<span>3</span>}</span><br><span>world[<span>'a'</span>] <span># will return 1</span></span><br><span></span><br><span>europe = {<span>'spain'</span>:<span>'madrid'</span>, <span>'france'</span>:<span>'paris'</span>, <span>'germany'</span>:<span>'berlin'</span>, <span>'norway'</span>:<span>'oslo'</span> }</span><br><span><span># print out the keys</span></span><br><span>europe.keys()</span><br><span></span><br><span><span># To add data into the existing dictionary</span></span><br><span>world[<span>'d'</span>] = <span>4</span></span><br><span><span>'d'</span> <span>in</span> world <span>#now this will return True</span></span><br><span><span># To update data in a dictionary</span></span><br><span>world[<span>'d'</span>] = <span>5</span></span><br><span><span># To delete a pair of values</span></span><br><span><span>del</span>(world[<span>'d'</span>])</span><br></pre></td></tr></tbody></table>
    
-   keys have to be unique.
    
-   keys have to be “immutable” objects. “Immutable” means that the objects’ content cannot be changed after they are created. e.g. strings, booleans, integers. But lists are mutable object, since you can change its content after its creation.

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br><span>7</span><br></pre></td><td><pre><span>world = {<span>0</span>:<span>'hello'</span>, <span>True</span>:<span>'dear'</span>, <span>'two'</span>:<span>'world'</span>} <span>#a valid dictionary</span></span><br><span></span><br><span>{[<span>'just'</span>, <span>'to'</span>, <span>'test'</span>]: <span>'value'</span>} <span>#invalid dictionary</span></span><br><span></span><br><span>europe = {<span>'spain'</span>:<span>'madrid'</span>, <span>'france'</span>:<span>'paris'</span>, <span>'germany'</span>:<span>'berlin'</span>, <span>'norway'</span>:<span>'oslo'</span> }</span><br><span><span># print out the keys</span></span><br><span>europe.keys()</span><br></pre></td></tr></tbody></table>

### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#List-vs-Dictionary "List vs Dictionary")List vs Dictionary

-   Similarity: select, update and remove: \[\]
-   Difference: list is indexed by range of numbers, while dictionary is indexed by unique keys.
-   for list, it should be used when there is:

1.  Collection of values
2.  where the order matters
3.  want to easily select entire subsets

-   for dictionary, it should be used when you need to lookup table with unique keys, and want the process to be quick.

### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Dictionary-of-dictionaries "Dictionary of dictionaries")Dictionary of dictionaries

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br><span>7</span><br><span>8</span><br><span>9</span><br><span>10</span><br><span>11</span><br><span>12</span><br></pre></td><td><pre><span>europe = { <span>'spain'</span>: { <span>'capital'</span>:<span>'madrid'</span>, <span>'population'</span>:<span>46.77</span> },</span><br><span>           <span>'france'</span>: { <span>'capital'</span>:<span>'paris'</span>, <span>'population'</span>:<span>66.03</span> },</span><br><span>           <span>'germany'</span>: { <span>'capital'</span>:<span>'berlin'</span>, <span>'population'</span>:<span>80.62</span> },</span><br><span>           <span>'norway'</span>: { <span>'capital'</span>:<span>'oslo'</span>, <span>'population'</span>:<span>5.084</span> } }</span><br><span><span># To subset element in the sub-dictionary</span></span><br><span>europe[<span>'france'</span>][<span>'capital'</span>]</span><br><span></span><br><span><span># Create sub-dictionary data</span></span><br><span>data = {<span>'capital'</span>:<span>'rome'</span>, <span>'population'</span>:<span>59.83</span>}</span><br><span></span><br><span><span># Add data to europe under key 'italy'</span></span><br><span>europe[<span>'italy'</span>] = data</span><br></pre></td></tr></tbody></table>

## [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Pandas "Pandas")Pandas

Pandas is a high level data manipulation tool that was built on Numpy. It can bring dataset down to tabular structure and store it in a **DataFrame**. Numpy array is not that useful in this case since the data in the table may be of different types.

### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#DataFrame-from-Dictionary "DataFrame from Dictionary")DataFrame from Dictionary

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br><span>7</span><br><span>8</span><br></pre></td><td><pre><span>d = {<span>'country'</span>:[<span>'Brazil'</span>, <span>'Russia'</span>, <span>'India'</span>],</span><br><span>  <span>'capital'</span>:[<span>'Brasilia'</span>, <span>'Moscow'</span>, <span>'New Delhi'</span>],</span><br><span>  <span>'area'</span>:[<span>8.516</span>, <span>17.10</span>, <span>3.286</span>],</span><br><span>  <span>'population'</span>:[<span>200.4</span>, <span>143.5</span>, <span>1252</span>]}</span><br><span><span>import</span> pandas <span>as</span> pd</span><br><span>brics = pd.DataFrame(d)</span><br><span><span>#To specify the row index</span></span><br><span>brics.index = [<span>'BR'</span>, <span>'RU'</span>, <span>'IN'</span>]</span><br></pre></td></tr></tbody></table>

### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#DataFrame-from-csv-file "DataFrame from csv file")DataFrame from csv file

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br></pre></td><td><pre><span><span>import</span> pandas <span>as</span> pd</span><br><span>brics = pd.read_csv(<span>"path/to/brics.csv"</span>, index_col = <span>0</span>) <span>#index_col = 0 helps to set the first column as the row index.</span></span><br></pre></td></tr></tbody></table>

### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Index-and-Select-Data "Index and Select Data")Index and Select Data

-   Square brackets: limited functionality
    
    <table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br><span>7</span><br></pre></td><td><pre><span><span>#Column Access</span></span><br><span>brics[<span>'country'</span>]<span># this is a pandas series, which can be thought as a 1d labelled array. Dataframe = pasting several series together</span></span><br><span>brics[[<span>'country'</span>]] <span>#this will keep the dataframe type</span></span><br><span>brics[[<span>'country'</span>, <span>'capital'</span>]]</span><br><span></span><br><span><span>#Row Access</span></span><br><span>brics[<span>1</span>:<span>4</span>] <span>#select row with index 1 to 3</span></span><br></pre></td></tr></tbody></table>
    
-   Advanced methods: loc(label-based), iloc(integer position-based)
    

**loc**  

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br><span>7</span><br><span>8</span><br><span>9</span><br><span>10</span><br></pre></td><td><pre><span><span>#Row access</span></span><br><span>brics.loc[<span>'RU'</span>] <span>#Row as pandas series</span></span><br><span>brics.loc[[<span>'RU'</span>]] <span>#row as dataframe</span></span><br><span>brics.loc[[<span>'RU'</span>, <span>'IN'</span>]]</span><br><span></span><br><span><span>#Row &amp; Column</span></span><br><span>brics.loc[[<span>'RU'</span>, <span>'IN'</span>], [<span>'country'</span>, <span>'capital'</span>]]</span><br><span></span><br><span><span>#Column access</span></span><br><span>brics.loc[:, [<span>'country'</span>, <span>'capital'</span>]]</span><br></pre></td></tr></tbody></table>

**iloc**  

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br><span>7</span><br><span>8</span><br><span>9</span><br><span>10</span><br><span>11</span><br><span>12</span><br><span>13</span><br><span>14</span><br></pre></td><td><pre><span><span>#Row access</span></span><br><span>brics.loc[[<span>'RU'</span>]] <span>#row as dataframe</span></span><br><span>brics.iloc[[<span>1</span>]] </span><br><span></span><br><span>brics.loc[[<span>'RU'</span>, <span>'IN'</span>]]</span><br><span>brics.iloc[[<span>1</span>, <span>2</span>]]</span><br><span></span><br><span><span>#Row &amp; Column</span></span><br><span>brics.loc[[<span>'RU'</span>, <span>'IN'</span>], [<span>'country'</span>, <span>'capital'</span>]]</span><br><span>brics.iloc[[<span>1</span>, <span>2</span>, <span>3</span>], [<span>0</span>, <span>1</span>]]</span><br><span></span><br><span><span>#Column access</span></span><br><span>brics.loc[:, [<span>'country'</span>, <span>'capital'</span>]]</span><br><span>brics.iloc[:, [<span>0</span>, <span>1</span>]]</span><br></pre></td></tr></tbody></table>

**ix** a way to combine loc and iloc (not covered in the course)

## [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Logic-Control-Flow-and-Filtering "Logic, Control Flow and Filtering")Logic, Control Flow and Filtering

### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Comparison-Operators "Comparison Operators")Comparison Operators

Comparison operators are operators that can tell how Python values relate, and results in a boolean

-   Numeric operators
    
    <table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br></pre></td><td><pre><span><span>2</span> &lt; <span>3</span></span><br><span><span>2</span> &gt; <span>3</span></span><br><span><span>2</span> == <span>3</span></span><br><span><span>2</span> &lt;= <span>3</span></span><br><span><span>2</span> &gt;= <span>3</span></span><br><span><span>2</span> != <span>3</span></span><br></pre></td></tr></tbody></table>
    
-   Other comparisons
    
    <table><tbody><tr><td><pre><span>1</span><br></pre></td><td><pre><span><span>'carl'</span> &lt; <span>'chris'</span> <span>#according to alphabet</span></span><br></pre></td></tr></tbody></table>
    
-   Boolean operators: and, or, not
    
    <table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br><span>7</span><br><span>8</span><br><span>9</span><br><span>10</span><br></pre></td><td><pre><span><span>#and</span></span><br><span><span>True</span> <span>and</span> <span>True</span> <span>#returns true</span></span><br><span>x = <span>12</span></span><br><span>x &gt; <span>5</span> <span>and</span> x &lt; <span>15</span> <span>#returns true</span></span><br><span></span><br><span><span>#or</span></span><br><span><span>False</span> <span>or</span> <span>True</span> <span>#returns true</span></span><br><span></span><br><span><span>#not</span></span><br><span><span>not</span> <span>True</span> <span>#returns false</span></span><br></pre></td></tr></tbody></table>
    

When working with Numpy: `logical_and()`, `logical_or()`, and `logical_not()`

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br></pre></td><td><pre><span>bmi = np.array([<span>21</span>,<span>852</span>, <span>20.975</span>, <span>21.75</span>, <span>24.757</span>, <span>21.441</span>])</span><br><span><span>#logical_and()</span></span><br><span>np.logical_and(bmi &gt; <span>21</span>, bmi &lt; <span>22</span>) <span>#returns an array of T/F</span></span><br><span>bmi[np.logical_and(bmi &gt; <span>21</span>, bmi &lt; <span>22</span>)] <span>#subset the desired data</span></span><br></pre></td></tr></tbody></table>

### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Conditional-Statements-if-else-elif "Conditional Statements: if, else, elif")Conditional Statements: if, else, elif

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br><span>7</span><br></pre></td><td><pre><span>z = <span>4</span></span><br><span><span>if</span> z % <span>2</span> == <span>0</span> :</span><br><span>    print(<span>'z is even'</span>) <span># if this statement is executed, the elif and else statements will not be executed.</span></span><br><span><span>elif</span> z % <span>3</span> == <span>0</span> :</span><br><span>    print(<span>'z is divisible by 3'</span>)</span><br><span><span>else</span> :</span><br><span>    print(<span>'z is odd'</span>) <span># no need speficication of condition</span></span><br></pre></td></tr></tbody></table>

### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Filtering-Pandas-DataFrame "Filtering Pandas DataFrame")Filtering Pandas DataFrame

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br></pre></td><td><pre><span>brics[brics[<span>'area'</span>] &gt; <span>8</span>] <span># select rows that satisfy the condition</span></span><br><span></span><br><span><span>import</span> numpy <span>as</span> np</span><br><span>brics[no.logical_and(brics[<span>'area'</span>] &gt; <span>8</span>, brics[<span>'area'</span>] &lt; <span>10</span>)]</span><br></pre></td></tr></tbody></table>

## [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Loops "Loops")Loops

### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#While-loop "While loop")While loop

While loops can help to repeat the if statement, and can be very helpful in some cases. For example, to repeat the same step over and over again until **a particular condition** is met, so that it can stop at some point.

Example

-   Error starts at 50
-   Divide error by 4 on every run
-   Continue until error no longer > 1
    
    <table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br></pre></td><td><pre><span>error = <span>50.0</span></span><br><span><span>while</span> error &gt; <span>1</span> :</span><br><span>    error = error / <span>4</span></span><br><span>    print(error)</span><br></pre></td></tr></tbody></table>
    

### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#For-loop "For loop")For loop

##### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Basics "Basics")Basics

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br><span>7</span><br><span>8</span><br><span>9</span><br><span>10</span><br><span>11</span><br><span>12</span><br><span>13</span><br><span>14</span><br><span>15</span><br><span>16</span><br><span>17</span><br><span>18</span><br><span>19</span><br><span>20</span><br><span>21</span><br><span>22</span><br></pre></td><td><pre><span>fam = [<span>1</span>,<span>73</span>, <span>1.68</span>, <span>1.71</span>, <span>1.89</span>]</span><br><span><span>for</span> height <span>in</span> fam :</span><br><span>    print(height)</span><br><span></span><br><span><span>#  To have access to the index</span></span><br><span><span>for</span> index, height <span>in</span> enumerate(fam) :</span><br><span>    print(<span>'index '</span> + str(index) + <span>': '</span> + str(height)) <span>#the output is like index 0: 1.73</span></span><br><span></span><br><span><span># loop over strings</span></span><br><span><span>for</span> c <span>in</span> <span>"family"</span></span><br><span>    print(c) <span>#print out each letter in the word</span></span><br><span></span><br><span><span># Example</span></span><br><span><span># house list of lists</span></span><br><span>house = [[<span>"hallway"</span>, <span>11.25</span>], </span><br><span>         [<span>"kitchen"</span>, <span>18.0</span>], </span><br><span>         [<span>"living room"</span>, <span>20.0</span>], </span><br><span>         [<span>"bedroom"</span>, <span>10.75</span>], </span><br><span>         [<span>"bathroom"</span>, <span>9.50</span>]]</span><br><span><span># Build a for loop from scratch</span></span><br><span><span>for</span> room <span>in</span> house:</span><br><span>    print(<span>'the '</span> + room[<span>0</span>] + <span>' is '</span> + str(room[<span>1</span>]) + <span>' sqm'</span>)</span><br></pre></td></tr></tbody></table>

##### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Looping-Data-Structures "Looping Data Structures")Looping Data Structures

-   Dictionary : use a method. `for key, val in my_dict.items() :`
-   Numpy Array: use a function. `for val in np.nditer(my_array) :`
-   DataFrame: use a method. `for lab, row in my_df.iterrows() :`
    
    <table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br><span>7</span><br><span>8</span><br><span>9</span><br><span>10</span><br><span>11</span><br><span>12</span><br><span>13</span><br><span>14</span><br><span>15</span><br><span>16</span><br><span>17</span><br><span>18</span><br><span>19</span><br><span>20</span><br><span>21</span><br><span>22</span><br><span>23</span><br><span>24</span><br><span>25</span><br><span>26</span><br><span>27</span><br><span>28</span><br><span>29</span><br><span>30</span><br><span>31</span><br><span>32</span><br><span>33</span><br><span>34</span><br><span>35</span><br><span>36</span><br><span>37</span><br><span>38</span><br><span>39</span><br><span>40</span><br><span>41</span><br><span>42</span><br><span>43</span><br><span>44</span><br><span>45</span><br></pre></td><td><pre><span><span># Dictionary</span></span><br><span>world = {<span>'afghanistan'</span>:<span>30.55</span>,</span><br><span>         <span>'albania'</span>:<span>2.77</span>,</span><br><span>         <span>'algeria'</span>:<span>39.21</span>}</span><br><span></span><br><span><span># To print out the keys and corresponding values</span></span><br><span><span>for</span> key, value <span>in</span> world.items() : <span>#key and value can also be changed into other forms, like k and v. But the position does matters. The first represents the key, the second represents the value.</span></span><br><span>    print(key + <span>' -- '</span> + str(value)) <span># the output will not follow the original order in the dictionary defined above, since dictionaries are inherently unordered</span></span><br><span></span><br><span><span># Numpy Arrays</span></span><br><span><span>import</span> numpy <span>as</span> np</span><br><span>np_height = np.array([<span>1</span>,<span>73</span>, <span>1.68</span>, <span>1.71</span>, <span>1.89</span>, <span>1.79</span>])</span><br><span>np_weight = np.array([<span>65.4</span>, <span>59.2</span>, <span>63.6</span>, <span>88.4</span>, <span>68.7</span>])</span><br><span>bmi = np_weight / np_height ** <span>2</span></span><br><span><span>for</span> val <span>in</span> bmi :</span><br><span>    print(val)</span><br><span></span><br><span><span>## 2D Numpy Arrays</span></span><br><span>meas = np.array([np_height, np_weight])</span><br><span><span>for</span> val <span>in</span> np.nditer(meas)</span><br><span>    print(val) <span>#the output will print out array by array</span></span><br><span></span><br><span><span># DataFrame</span></span><br><span><span>import</span> pandas <span>as</span> pd</span><br><span>brics = pd.read_csv(<span>'brics.csv'</span>, index_col = <span>0</span>)</span><br><span></span><br><span><span>for</span> val <span>in</span> brics :</span><br><span>    print(val) <span>#this will only print out the column names</span></span><br><span></span><br><span><span># to loops each row in a dataframe: iterrows(). </span></span><br><span><span>for</span> lab, row <span>in</span> brics.iterrows() : <span>#lab is the row index, and row is the data in the specific row.</span></span><br><span>    print()</span><br><span></span><br><span><span>## Selective print</span></span><br><span><span>for</span> lab, row <span>in</span> brics.interrows() :</span><br><span>    print(lab + <span>': '</span> + row[<span>'capital'</span>])</span><br><span></span><br><span><span>## Add column to the existing dataframe</span></span><br><span><span>for</span> lab, row <span>in</span> brics.iterrows() : </span><br><span>    brics.loc[lab, <span>'name_length'</span>] = len(row[<span>'country'</span>]) <span>#inefficient when the dataset is large, since it creates a series in each iteration</span></span><br><span></span><br><span><span>### Using Apply without using for loops</span></span><br><span>brics[<span>'name_length'</span>] = brics[<span>'country'</span>].apply(len)</span><br><span><span>### When applying a method instead of a function</span></span><br><span>cars[<span>'COUNTRY'</span>] = cars[<span>'country'</span>].apply(str.upper)</span><br></pre></td></tr></tbody></table>
    

Tips:

1.  `print(x, end = ' ')` the end argument specify the interval between this printout and the next printout

## [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Case-Study-Hacker-Statistics "Case Study: Hacker Statistics")Case Study: Hacker Statistics

### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#To-generate-random-numbers "To generate random numbers")To generate random numbers

`np.random.seed(123)` same seed will generate the same set of random numbers and ensures reproducibility  
`np.random.rand()` this will generate random numbers from 0 to 1  
`np.random.randint(0, 2)` this will randomly generate 0 or 1, since 2 will not be included  

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br><span>7</span><br><span>8</span><br><span>9</span><br><span>10</span><br><span>11</span><br><span>12</span><br><span>13</span><br><span>14</span><br><span>15</span><br><span>16</span><br><span>17</span><br><span>18</span><br><span>19</span><br><span>20</span><br><span>21</span><br></pre></td><td><pre><span><span># Import numpy and set seed</span></span><br><span><span>import</span> numpy <span>as</span> np</span><br><span>np.random.seed(<span>123</span>)</span><br><span></span><br><span><span># Starting step</span></span><br><span>step = <span>50</span></span><br><span></span><br><span><span># Roll the dice</span></span><br><span>dice = np.random.randint(<span>1</span>,<span>7</span>)</span><br><span></span><br><span><span># Finish the control construct</span></span><br><span><span>if</span> dice &lt;= <span>2</span> :</span><br><span>    step = step - <span>1</span></span><br><span><span>elif</span> dice &lt; <span>6</span>:</span><br><span>    step = step + <span>1</span></span><br><span><span>else</span> :</span><br><span>    step = step + np.random.randint(<span>1</span>, <span>7</span>)</span><br><span></span><br><span><span># Print out dice and step</span></span><br><span>print(dice)</span><br><span>print(step)</span><br></pre></td></tr></tbody></table>

### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Simulate-random-walk "Simulate random walk")Simulate random walk

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br><span>7</span><br><span>8</span><br><span>9</span><br><span>10</span><br><span>11</span><br><span>12</span><br><span>13</span><br><span>14</span><br><span>15</span><br><span>16</span><br><span>17</span><br><span>18</span><br><span>19</span><br><span>20</span><br><span>21</span><br><span>22</span><br></pre></td><td><pre><span><span># Import numpy and set seed</span></span><br><span><span>import</span> numpy <span>as</span> np</span><br><span>np.random.seed(<span>123</span>)</span><br><span></span><br><span><span># Initialize random_walk</span></span><br><span>random_walk = [<span>0</span>]</span><br><span></span><br><span><span>for</span> x <span>in</span> range(<span>100</span>) :</span><br><span>    step = random_walk[<span>-1</span>]</span><br><span>    dice = np.random.randint(<span>1</span>,<span>7</span>)</span><br><span></span><br><span>    <span>if</span> dice &lt;= <span>2</span>:</span><br><span>        <span># use max to make sure step can't go below 0</span></span><br><span>        step = max(<span>0</span>, step - <span>1</span>)</span><br><span>    <span>elif</span> dice &lt;= <span>5</span>:</span><br><span>        step = step + <span>1</span></span><br><span>    <span>else</span>:</span><br><span>        step = step + np.random.randint(<span>1</span>,<span>7</span>)</span><br><span></span><br><span>    random_walk.append(step)</span><br><span></span><br><span>print(random_walk)</span><br></pre></td></tr></tbody></table>

### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Visualize-the-random-walk "Visualize the random walk")Visualize the random walk

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br><span>7</span><br><span>8</span><br></pre></td><td><pre><span><span># Import matplotlib.pyplot as plt</span></span><br><span><span>import</span> matplotlib.pyplot <span>as</span> plt</span><br><span></span><br><span><span># Plot random_walk</span></span><br><span>plt.plot(random_walk)</span><br><span></span><br><span><span># Show the plot</span></span><br><span>plt.show()</span><br></pre></td></tr></tbody></table>

### [](https://joannaoyzl.github.io/2018/05/23/Intermediate-Python/#Distribution "Distribution")Distribution

What is the chance that you can reach 60 steps after throwing the dice for 100 times?

-   Each random walk has an end point
-   Simulate this walk 10,000 times, then you get 10,000 end points: Distribution
-   Calculate the chances

Create a list that contains the path of 10 random walks and visualize it  

<table><tbody><tr><td><pre><span>1</span><br><span>2</span><br><span>3</span><br><span>4</span><br><span>5</span><br><span>6</span><br><span>7</span><br><span>8</span><br><span>9</span><br><span>10</span><br><span>11</span><br><span>12</span><br><span>13</span><br><span>14</span><br><span>15</span><br><span>16</span><br><span>17</span><br><span>18</span><br><span>19</span><br><span>20</span><br><span>21</span><br><span>22</span><br><span>23</span><br><span>24</span><br><span>25</span><br><span>26</span><br><span>27</span><br><span>28</span><br><span>29</span><br><span>30</span><br><span>31</span><br><span>32</span><br></pre></td><td><pre><span><span>import</span> matplotlib.pyplot <span>as</span> plt</span><br><span><span>import</span> numpy <span>as</span> np</span><br><span>np.random.seed(<span>123</span>)</span><br><span>all_walks = []</span><br><span><span>for</span> i <span>in</span> range(<span>10</span>) :</span><br><span>    random_walk = [<span>0</span>]</span><br><span>    <span>for</span> x <span>in</span> range(<span>100</span>) :</span><br><span>        step = random_walk[<span>-1</span>]</span><br><span>        dice = np.random.randint(<span>1</span>,<span>7</span>)</span><br><span>        <span>if</span> dice &lt;= <span>2</span>:</span><br><span>            step = max(<span>0</span>, step - <span>1</span>)</span><br><span>        <span>elif</span> dice &lt;= <span>5</span>:</span><br><span>            step = step + <span>1</span></span><br><span>        <span>else</span>:</span><br><span>            step = step + np.random.randint(<span>1</span>,<span>7</span>)</span><br><span>        <span># Implement clumsiness (there is a 0.001 chance that the climber will fall and restart from 0 step)</span></span><br><span>        <span>if</span> np.random.rand(<span>0</span>, <span>1</span>) &lt;= <span>0.001</span> :</span><br><span>            step = <span>0</span></span><br><span>        random_walk.append(step)</span><br><span>    all_walks.append(random_walk)</span><br><span></span><br><span>np_aw = np.array(all_walks) <span># Convert all_walks to Numpy array: np_aw</span></span><br><span>plt.plot(np_aw)</span><br><span>plt.show()</span><br><span>plt.clf() <span># Clear the figure</span></span><br><span>np_aw_t = np.transpose(np_aw)<span># Transpose np_aw: np_aw_t. This will make each row contains the 1st, 2nd, 3rd... random step in all the random walks.</span></span><br><span>plt.plot(np_aw_t)</span><br><span>plt.show()</span><br><span></span><br><span>ends = np_aw_t[<span>-1</span>] <span># Select last row from np_aw_t: ends</span></span><br><span>plt.hist(ends)<span># Plot histogram of ends, display plot</span></span><br><span>plt.show()</span><br></pre></td></tr></tbody></table>