# Classes and Objects
__***Objects are an encapsulation of variables and functions into a single entity. Objects get their variables and functions from classes. Classes are essentially a template to create your objects.**__


    class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

        In [1]: 

 __**We'll explain why you have to include that "self" as a parameter a little bit later. First, to assign the above class(template) to an object you would do the following:**__

        class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

    myobjectx = MyClass()

    In [1]: 


__**Now the variable "myobjectx" holds an object of the class "MyClass" that contains the variable and the function defined within the class called "MyClass".**__

## Accessing Object Variables

__**To access the variable inside of the newly created object "myobjectx" you would do the following:**__

    class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

    myobjectx = MyClass()

    myobjectx.variable

    Out[1]: 'blah'

    In [1]: 

__**So for instance the below would output the string "blah":**__

    class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

    myobjectx = MyClass()

    print(myobjectx.variable)

    blah

    In [1]: 

__**You can create multiple different objects that are of the same class(have the same variables and functions defined). However, each object contains independent copies of the variables defined in the class. For instance, if we were to define another object with the "MyClass" class and then change the string in the variable above:**__

    class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

    myobjectx = MyClass()
    myobjecty = MyClass()

    myobjecty.variable = "yackity"

    # Then print out both values
    print(myobjectx.variable)
    print(myobjecty.variable)


    blah
    yackity

    In [1]: 

# Thinking Recursively in Python

__**Problems (in life and also in computer science) can often seem big and scary. But if we keep chipping away at them, more often than not we can break them down into smaller chunks trivial enough to solve. This is the essence of thinking recursively, and my aim in this article is to provide you, my dear reader, with the conceptual tools necessary to approach problems from this recursive point of view.**__

## Dear Pythonic Santa Claus…
__**I realize that as fellow Pythonistas we are all consenting adults here, but children seem to grok the beauty of recursion better. So let’s not be adults here for a moment and talk about how we can use recursion to help Santa Claus.**__

![santa](https://files.realpython.com/media/santa_claus_2.ecbf2686f1a1.png)


    houses = ["Eric's house", "Kenny's house", "Kyle's house", "Stan's house"]

    def deliver_presents_iteratively():
    for house in houses:
        print("Delivering presents to", house)  

        >>> deliver_presents_iteratively()
    Delivering presents to Eric's house
    Delivering presents to Kenny's house
    Delivering presents to Kyle's house
    Delivering presents to Stan's house

__**But I feel for Santa. At his age, he shouldn’t have to deliver all the presents by himself. I propose an algorithm with which he can divide the work of delivering presents among his elves:**__

![age](https://robocrop.realpython.net/?url=https%3A//files.realpython.com/media/elves_7.8d1af1cd85c8.png&w=1918&sig=24bad525e070e8248cc8fcce28fc3f52c68a69f9)

### Maintaining State

__When dealing with recursive functions, keep in mind that each recursive call has its own execution context, so to maintain state during recursion you have to either:__

* Thread the state through each recursive call so that the current state is part of the current call’s execution context
* Keep the state in global scope