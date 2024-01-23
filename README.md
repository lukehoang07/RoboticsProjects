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

# Working with Files
Sometimes the data you're given is not in a python file. Sometimes it in a formate like JSON, TOML, CSV, or a database file. Python comes with different ways to read this information and create Python objects out of them.

## Opening a File
This first thing that you will always need to do is open a file, then read the contents. Python comes with a nice, easy way to open, read, and close files all at once. You can do this with the <code>with</code> statement. Here's the general structure:

```py
with open("path/to/file.json", "r") as f:
  content = f.read()
print(f)
```

This is how you fetch a string of the file you want. It is important to know basic eascape codes. Here's a question: what defines a line in a file? The answer is simple: \n. That means newline, and sperates the lines in a file. So, if you ```.split("\n")``` on the file string, you can loop through the lines.

### JSON
Sometimes file are structured in a specific way, and python can create objects out of it by itself. The best example is JSON. That stands for JavaScript Object Notation. It is really common for storing data. [Here] (https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/JSON) is some stuff to learn JSON. 

The first thing that you need to do is import the ```json``` library in your file. Normally, libraries go at the very top of the file. Then, you call ```json.loads(<json_str>)``` to make an object out of the data provided. Here's an example:

#### ex.json
```json
{
  "name": "Anthony",
  "age": 16,
  "classes": [
    {"name": "MI", "teacher": "Smith"},
    {"name": "Trig. H.", "teacher": "Williams"}
  ]
}
```

#### run.py
```py
import json

with open("ex.json", "r") as f:
  content = f.read()

jsonDict = json.loads(content)
print(f"Hi, I am {jsonDict['name']}, am I'm {jsonDict['name']}yo")
for class in jsonDict['classes']:
  print(class['name'], class['teacher'])
```
