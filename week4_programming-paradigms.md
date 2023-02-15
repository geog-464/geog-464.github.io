In Python, everything is considered an object. This includes **classes**, **instances** of classes, **modules**, and **functions**. A variable can reference any object.

How you utilize objects is up to you. We tend to arrange objects and have them interact in what some call "the three 'original' logical structures: *Sequence*, *Alternative Selection*, and *Loops*", which come together to make algorithms.

> All of our modern languages follow the rules of structure: Unless a 'control' statement is executed each statement is executed in sequence.  Control statements are used instead of *GOTO* statements to make alternative selections and loops.  Parts of programs are related to one-another using only these logical structures. ([Saunders 2017](#references))

# Programming Paradigms

The *way in which you code* (your style) can usually be summed up using today's well-recognized programming paradigms: **procedural**, **functional**, and **object-oriented** (OOP).

A programming paradigm is **a way of programming**, or **a set of principles used to design programming languages and frameworks** (it can provide a methodology for writing software). Some languages are better suited for use with certain approaches over others. Python can be used with several of them, which we will review here.


```python
#--------------------
#example procedural
#--------------------

numbers = [1, 2, 3, 4, 5]
squared_numbers = []
for number in numbers:
    squared_numbers.append(number * number)
print(squared_numbers)

#--------------------
#example functional
#--------------------

def square(x):
    return x * x

numbers = [1, 2, 3, 4, 5]
squared_numbers = list(map(square, numbers))
print(squared_numbers)

#--------------------
#example object-oriented
#--------------------

class SquareNumbers:
    def __init__(self, n):
        self.numbers = n
        self.squared_numbers = []

    def square_numbers(self):
        for number in self.numbers:
            self.squared_numbers.append(number * number)
        return self.squared_numbers

numbers = [1, 2, 3, 4, 5]
squared_numbers_obj = SquareNumbers(numbers)
print(squared_numbers_obj.square_numbers())

#There is also such thing as structural programming and logical programming. However, whereas these were once programming styles, most modern programming languages can be considered stuctures in the first place (modular design through the use of modules and packages, etc.). Logical programming, on the other hand, 

```

    [1, 4, 9, 16, 25]
    [1, 4, 9, 16, 25]
    [1, 4, 9, 16, 25]


As a Jupyter user growing into a data science workflow specialized in geospatial, you are likely to develop a habit of programming procedurally. However, you may be inclined to develop towards functional or OOP the more you code.

## 1. Procedural programming

Procedural programming involves breaking down a task into a series of steps, or instructions, to be executed in sequence. It focuses on the execution of code as a series of actions, without organizing it into logical groups or objects (as done in other paradigms discussed here). The focus is on coding the necessary operations in the correct order.

In procedural programming, data and methods are treated as separate entities. This lack of access specifiers can make it less secure compared to object-oriented programming. However, incorporating functions from functional programming is not prohibited as the goal of procedural programming is not to avoid using specific structures, but rather to follow a set sequence of steps for code to achieve its purpose.

The aim of this approach is not to completely reject functions, objects, or any other programming paradigm, as each serves its own purpose. Instead, the focus is to have the code follow a set sequence of steps, creating a narrative for the code to achieve its purpose.

- Pros:
  - Good for general-purpose programming.
  - Simple, intuitive, and straightforward way of writing sequential code – great for people just starting out with programming.
  - Easily applied in interpreters.
  - Easy to track program flow, unlike in paradigms like OOP, where you end up keeping track of multiple classes and objects while understanding how they interact in the code.
- Cons:
  - Not very reusable
  - Not very scalable
  - Not secure (e.g. scope issues)
  - Quite verbose (not concise)

Example: procedural vs. functional


```python
#procedural
#--------------------
# Calculate total in the list
total = 0
myList = [1,2,3,4,5]

# Create a for loop to add numbers in the list to the total
for x in myList:
    total += x
print(total)

#functional
#--------------------
mylist = [1,2,3,4,5]

# set total to the sum of numbers in mylist
total = sum(mylist)
print(total + 3)
```

    15
    18


## 2. Functional programming

In the procedural programming approach, the focus is on breaking down a problem into a series of steps and executing these steps in a specific order to solve the problem. The procedural program uses procedures or functions to accomplish specific tasks, and the program's state and data are manipulated through variables. Procedures simply **execute commands**.

By contrast, **functions return values** ([Krijthe 2009](#references)). In functional programming, the focus is on breaking down a problem into exclusively a series of functions that take inputs, process data and return outputs. The state and data are treated as immutable, and the functions are combined to form the solution to the problem. This approach emphasizes the use of pure functions, leading to code that is easier is break down, test, and debug. The emphasis is on immutability, avoiding shared state and side effects, and using functions as the main building blocks for solving problems.

> Python in recent years has acquired built-in support for functional programming—a set that by most measures includes generators, comprehensions, closures, maps, decorators, anonymous function lambdas, and first-class function objects ([Lutz 2013, 16](#references))

- Main points:
    - Functional programming is centered around using functions to organize code. It is therefore more concise (and readable, according to some) than procedural code.
    - Functions should have a clear, singular purpose, meaning they always produce the same output given their inputs (referential transparency).
    - Code is broken down into single-responsibility, reusable functions that receive data parameters, process them locally without affecting or depending on the global state, and return results for use in the program.
    - This is captured by the concept of **pure functions**, which are key to functional programming. A pure function always returns the same output based on its inputs.
    - By contrast, **impure functions** can have side effects (alter variables beyond their scope), use global variables, and can therefore produce variable results.

- Pros:
    - Reliable (pure functions)
    - Transparent (explicit passing of parameters to documented functions)
    - Easier debugging: variables only change at points at which they are passed between functions.

- Cons:
    - Less computationally efficient (functions, required at every step, duplicate data)
    - Less intuitive (can rely a lot on recursion)


Demonstration of a "pure" versus an "impure" function, scope, arguments (positional- and keyword-) and parameters:


```python
x = 0

def pure_sum(a, b):
    return a + b

age = input("What is your age? ")
yrs_left = input("In how many years will you graduate? ")

print("You will be " + pure_sum(age, yrs_left) + " years old when you graduate.")
```


```python
#1. solution: print("You will be " + str(pure_sum(int(age), int(yrs_left))) + " years old when you graduate.")
#2. demonstrate: def impure_sum(a, b):
#    return a + b + x
#3. How to make it pure again? declare x locally (inside the function)
```

## 3. Object-oriented programming



In OOP, developers can structure their software into modular and reusable components called classes and objects. These blueprint-like structures dictate a common structure for code entities, enabling them to conform and identify themselves accordingly.

Most objects represent a specific instance of a blueprint known as a class. The object is created using the class as a model and contains both data and functions specific to that object. For example, consider a class called "city" which could have attributes such as name, population, country, area, and methods such as grow and shrink. Each instance of the "city" class, or object, would have its own unique set of values for these attributes and could utilize the class's methods. The class acts as a blueprint for the objects, providing a common structure for the objects to follow and identify themselves with.

- Components:
  - Classes
  - Class instances (confusingly referred to by many as objects)
  - And their:
    - Attributes
    - Methods

- Pros
    - Reusability (great for building packages)
    - Security (encapsulation of functionality means it's limited to operating within that class instance and is also hidden)
    - Maintenance (modular, easier to identify issues and where they are)
    - Inheritance (classes created from existing classes inherit their attributes and methods)
        - To create a class that inherits another class's qualities, pass the parent-class to this child-class as a parameter.
- Cons:
    - Requires a lot of planning (usually a result of refactoring)
    - Usually heavy, large programs
    - Flow isn't obvious
    - Steep learning curve


```python
class Person:
  def __init__(self, fname, lname):
    self.firstname = fname
    self.lastname = lname

  def printname(self):
    print(self.firstname, self.lastname)

#Use the Person class to create an object, and then execute the printname method:

x = Person("Jo", "Blo")
x.printname()

class Student(Person):
    pass
y = Student("Bo", "Jlo")
y.printname()
```


```python
#--------------------
#example object-oriented
#--------------------

class SquareNumbers:
    def __init__(self, numbers):
        self.numbers = numbers
        self.squared_numbers = []

    def square_numbers(self):
        for number in self.numbers:
            self.squared_numbers.append(number * number)
        return self.squared_numbers

numbers = [1, 2, 3, 4, 5]
squared_numbers_obj = SquareNumbers(numbers)
print(squared_numbers_obj.square_numbers())

#return value of the method () vs the method itself.
```

### Classes

- A class is a template or blueprint for creating objects.
- Class objects provide default behavior and serve as factories for instance objects
- Like `def` statements for functions, `class` statements are run and stored in memory to be accessed whenever a new instance object is made from that class
- Assignments (variable or function declarations) inside class objects make up their attributes and methods respectively and can be accessed via `object.attribute` or, in the case of a method, `object.method()`
- Classes are defined by their attributes and methods.
- Variables representing classes in Python are usually capitalized (this is by convention, not enforced)
- Every time an object is created from a class, the **\_\_init\_\_** function is invoked. The purpose of the **\_\_init\_\_** method is solely to initialize the attributes of the object: it is only used within classes. This special method is known as Python's *constructor*, since it defines the construction plans for objects built from a given class.

Understanding classes helps you understand how Python itself is built. For example:
- `str`,`int`,`float`,`list` (etc.) are data types that are built in to Python (*built-in types*). However, they are essentially classes (albeit special classes). **Why are they special?** They are implemented at C-level code (Python is built on top of C). So they are not defined using the same syntax and methods as Python classes, including the \_\_init\_\_ method.

In this sense, creating your own classes is like creating new built-in data types for your program. However, you used Python syntax to do it (i.e. an \_\_init\_\_ method).

### Instances

- Also known confusingly as simply objects
- Objects are created as instances of classes (why we can call them *instance objects*)
- Instance objects are the real objects your programs process—each is a namespace in its own right, but inherits (i.e., has automatic access to) names in the class from which it was created. 
- instances come from calls; each time you call a class, you get a new instance of that class. (like declaring a variable!)

## Note: In-place methods

> \[...\] there are objects and operations that perform in-place object changes—Python’s mutable types, including lists, dictionaries, and sets. ([Lutz 2013, 181](#references))

- For in-place change operations like append, insert, del, and pop, no new list is created in memory, so execution is quick

## To conclude:

You may have noticed how fundamentally different the above-described paradigms are. Some appear more suitable for making software packages (object-oriented), whereas others are more explicitly narrative and maybe more appropriate for code notebooks (functional and some procedural approaches).

These paradigms can be grouped into two broader, more fundamental paradigms:
- **Imperative programming** prioritizes "how to do it" over "what to do." ([Zotti, 2015](#references))
  - It is the oldest and most basic programming approach.
  - It is used in low-level activities such as algorithm engineering.
  - It can also be used in more narrative, code notebooks because of its descriptive and inuitive qualities (procedural)!
  - OOP is also known to be imperative.
- **Declarative programming** focuses on "what to do" rather than "how to do it"
  - This describes functional programming quite well.
  - often used in web development when working with frameworks.


These groupings may clarify but also confuse. They are not fixed, and some of them could easily be descibed as subsets of others. They serve as descriptors for shedding light on the many styles of code you might observe in algorithms and software across all programming languages. They can also be useful to think about when concieving a project, as each has its own appropriate use cases.

---



## Sidenote: Modules

Modules help you organize your code.
- A module is essentially a Python file (.py) that contains Python code.
- Usually it's a Python file that is specifically intended for importing, but they can technically also be executed.
- Modules can contain class, funtion, and variables definitions.
- Modules often contain classes, which have their own methods and attributes (this can be confusing).
- When you import a module, you import it as an object that is made globally available to your code
- You can call its attributes (variables, functions) by referring to it in much the same way you refer to objects made from classes.
- Modules are imported using the `import` statement, after which they need to be called by referring to what you named them on import (e.g. `import pandas as pd`)
- Making your code reusable and organizing it into modules is an excellent way to build your programming arsenal and save time down the line.
- *Package modules* are when you import an entire directory of modules. This works in basically the same way, except you are importing a whole program (package, library).
- You can also import individual subpackages (folders) or modules (.py) from package modules by importing them explicitly (e.g. import matplotlib.pyplot as plt)



```python
#the functionality for converting 
from decimal import Decimal

print(Decimal("3.4"))

#or

#from decimal import *
#print(Decimal(1) / Decimal(3))

#---------------------
#show us the module
#import decimal
#print(decimal)
```

# Pandas dataframes

Let's explore a familiar package and see how some of these concepts may apply:


```python
import pandas as pd
```

![image.png](attachment:65bd15f7-3e64-4136-bece-99bbe0095166.png)

src: https://dbader.org/blog/meaning-of-underscores-in-python


```python
df = pd.read_csv("megacities.csv")
```


```python
type(df)
```




    pandas.core.frame.DataFrame




```python
pd.core.frame.DataFrame
```




    type



 When you use dot notation, you indicate to Python that you want to either run a particular operation on, or to access a particular property of, an object type. 


```python
#df.head(6)
#df.tail(6)

#df.columns
#df.dtypes
#df.describe()
#only gets called on ints & floats
#df.describe(include='object')
#use above to include other types

#filtering columns (dont title your headers with spaces!) is like accessing an attribute of a class or var from a module
#df.city
#df['city']

#range of columns
#df[['city','population']]

#more on filtering, loc methods, iloc, in the lab!

df[(df['country'] == ' China') & (df['population'] > 20000000)]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>city</th>
      <th>country</th>
      <th>latitude</th>
      <th>longitude</th>
      <th>population</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>Shanghai</td>
      <td>China</td>
      <td>31.246027</td>
      <td>121.483385</td>
      <td>25582000</td>
    </tr>
  </tbody>
</table>
</div>



# <a id='references'>References</a>

Krijthe, T. (2009). What is the difference between a "function" and a "procedure"?. Stackoverflow. Online at: https://stackoverflow.com/a/721107

Lutz, M. (2013). Learning Python (5th Edition). O'Reilly

Saunders, G. (2017). Logical Structures. Virginia Commonwealth University (VCU). Online at: http://www.people.vcu.edu/~gasaunde/structure.htm

Zotti, A. (2015). The Differences Between Procedural, Functional, Imperative, and Declarative Programming Paradigms. Github. Online at: https://amzotti.github.io/programming%20paradigms/2015/02/13/what-is-the-difference-between-procedural-function-imperative-and-declarative-programming-paradigms/
