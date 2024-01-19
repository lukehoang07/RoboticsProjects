# Robotics Projects
This is a repo for the Projects in robotics. I will add folders for the names of each project. Each day you should create a branch of that days date and your group name \[all lowercase] (yyyy-mm-dd-name). Each day you should merge your banch into main, and delete that branch. You and your partner should not work in the same file. Instead, use <code>import</code> to use each other's <code>class</code>s, <code>functions</code>, and variables.

# How to import
In the case that you need to use each other's work, you should import their code. My sugestion is that you create one main <code>class</code>, and put all the functions you want inside it. That makes using each other's functions a lot easiear. When using the other's class, you need to create an instance. You can do this without have to provide information into it. Here is an example:

### File/Partner A (fileA.py)
```py
class A:
  def addNumbers(self, x, y):
    return x + y

  def subtractNumbers(self, x, y):
    return x - y
```

### File/Partner B (fileB.py)
```py
from fileA import A
# from [file name without .py] import [class/function/variable name]

x = 10
y = 9

Functions = A()

print(Functions.addNumbers(x, y))
print(Functions.subtractNumbers(x, y))
```

# Workflow
When working on a project like this, it is essential that you create a workflow plan. Since we are borken into groups of two, each one of you should have a part. Here's how I'd do it.
* Person A: Skeletonizer
  * Creats skeleton classes and functions
  * Does more higher-level coding
  * (Coding Oriented)
* Person B: Data Infuser
  * Uses the classes and functions from the Skeletonizer to analyze the data
  * Creats objects from data, process data with functions, creats output in terminal and in files
  * (Logic Oriented)

# Documenting your Code \[Optional]
## Variable Definition
If you want your code to look a little more sophisticated, you can document your code in a few different ways. First off, you can add the type of a variable. To do so, you add a colon and they id for the type you specify. Below are some examples. A bar (<code>|</code>)means 'or', meaning that it can be any type. If you specify <code>list</code>, you can add the types allowed in your list in brackets afterward. This is useful for two reasons. First, the interpretor (the coding program) will tell you what your variable type is. Second, it can be used to find errors in types easier, because you know what you want and you're not getting it. Lastly, you can define a variable <i>without</i> an inital value if you use this.

```py
# normal types
var:str = "String"
var:int = 100
var:float = 6.9
var:dict = {"one": 1, "two": 2}
var:list = [1, 2, 3]
# you can specifiy what types are in a list!
var:list[str] = ["A", "B"]
var:list[str|int] = ["A", 1]
# A tuple is like a list that you can't modify. Indexed in the same way.
var:tuple = (1, 2)
# really useful for functions/methods! The coder will tell you what to input!
def add(x:int, y:int):
  return x + y
```

## Function Info
Another useful thing is to add more information. This is done in two ways.
### Return type
In the header of the function, if you add <code>-></code> after the parenthises for your parameters, you can tell people what your function should return. Make sure that it matches what you want! After the arrow, add the type afterwards. The following example tells me that the function returns an integar.

```py
def add(x:int, y:int) -> int:
  return x + y
```

### Summary
Summaries are great for people who do not know what you programmed. They are strings that dirrectly follow the header on the next line. If you want to span multiple lines, use three quotation marks. Make sure that it's arccurate to what the function/method does. Some things to add are what the inputs are, and what you return.

```py
def add(x:int, y:int) -> int:
  """Returns the sum of x and y

  Args:
    x:int - left number
    y:int - right number

  Returns:
    Sum of x and y
  """
  return x + y
```

## Documented Example
```py
def tonysEquation(x:int|float, y:int|float, m:int|float, d:int|float) -> float:
  """Takes the sum of two numbers x and y, multiplies them by m, divides them by d, and returns the resault.

  Args:
    x:int|float - left additive
    y:int|float - right additive
    m:int|float - right factor
    d:int|float - right divider

  Returns:
    ((x+y)*m)/d
  """
  sum:int = x + y
  product:int = sum * m
  dividend:float = product / d
  return dividend
```
