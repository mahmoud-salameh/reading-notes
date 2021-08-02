# List Comprehensions in Python

It consists of brackets containing an expression followed by a for clause, then
zero or more for or if clauses. The expressions can be anything, meaning you can
put in all kinds of objects in lists.

The list comprehension always returns a result list.

__If you used to do it like this:__

    new_list = []
    for i in old_list:
    if filter(i):
        new_list.append(expressions(i))

**You can obtain the same thing using list comprehension. Notice the append method has vanished!**

    new_list = [expression(i) for i in old_list if filter(i)]


## Examples

__Now when we know the syntax of list comprehensions, let’s show some examples and
how you can use it.__

__**Create a simple list**__

    x = [i for i in range(10)]
    print x

    # This will give the output:
    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]


__**Create a list using loops and list comprehension**__


For the next example, assume we want to create a list of squares. Start with an empty list.

# You can either use loops:
    squares = []

    for x in range(10):
    squares.append(x**2)
 
    print squares
    [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

    # Or you can use list comprehensions to get the same result:
    squares = [x**2 for x in range(10)]

    print squares
    [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]


__**Multiplying parts of a list**__

Multiply every part of a list by three and assign it to a new list.

    list1 = [3,4,5]
 
    multiplied = [item*3 for item in list1] 
 
    print multiplied 
    [9,12,15]

__**Using list comprehension in functions**__

Now, let’s see how we can use list comprehension in functions.

    # Create a function and name it double:
    def double(x):
  return x*2

    # If you now just print that function with a value in it, it should look like this:
    >>> print double(10)
    20

We can easily use list comprehension on that function.

    >>> [double(x) for x in range(10)]

    print double
    [0, 2, 4, 6, 8, 10, 12, 14, 16, 18]

    # You can put in conditions:

    >>> [double(x) for x in range(10) if x%2==0]
    [0, 4, 8, 12, 16]

    # You can add more arguments:

    >>> [x+y for x in [10,30,50] for y in [20,40,60]]
    [30, 50, 70, 50, 70, 90, 70, 90, 110]