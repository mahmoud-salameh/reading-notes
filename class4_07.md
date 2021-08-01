# Python Scope & the LEGB Rule: Resolving Names in Your Code

__**The concept of scope rules how variables and names are looked up in your code. It determines the visibility of a variable within the code. The scope of a name or variable depends on the place in your code where you create that variable. The Python scope concept is generally presented using a rule known as the LEGB rule.**__

## Understanding Scope

__In programming, the scope of a name defines the area of a program in which you can unambiguously access that name, such as variables, functions, objects, and so on. A name will only be visible to and accessible by the code in its scope. Several programming languages take advantage of scope for avoiding name collisions and unpredictable behaviors. Most commonly, you’ll distinguish two general scopes:__

1. 
Global scope: The names that you define in this scope are available to all your code.
2. Local scope: The names that you define in this scope are only available or visible to the code within the scope.

__Scope came about because early programming languages (like BASIC) only had global names. With this kind of name, any part of the program could modify any variable at any time, so maintaining and debugging large programs could become a real nightmare. To work with global names, you’d need to keep all the code in mind at the same time to know what the value of a given name is at any time. This was an important side-effect of not having scopes.__

__Some languages like Python use scope to avoid this kind of problem. When you use a language that implements scope, there’s no way for you to access all the variables in a program at all locations in that program. In this case, your ability to access a given name will depend on where you’ve defined that name.__

## Names and Scopes in Python

__Since Python is a dynamically-typed language, variables in Python come into existence when you first assign them a value. On the other hand, functions and classes are available after you define them using def or class, respectively. Finally, modules exist after you import them. As a summary, you can create Python names through one of the following operations:__

|Operation|Statement|
|---|---|
|Import operations|import module or from module import name|
|Function definitions|def my_func(): ...|
|Argument definitions in the context of functions|def my_func(arg1, arg2,... argN): ...|
|Class definitions|class MyClass: ...|

__All these operations create or, in the case of assignments, update new Python names because all of them assign a name to a variable, constant, function, class, instance, module, or other Python object.__

__**For example, if you assign a value to a name inside a function, then that name will have a local Python scope. In contrast, if you assign a value to a name outside of all functions—say, at the top level of a module—then that name will have a global Python scope.**__

    import sys
    sys.__dict__.keys()
    dict_keys(['__name__', '__doc__', '__package__',..., 'argv', 'ps1', 'ps2'])

**After you import sys, you can use .keys() to inspect the keys of sys.__ dict __. This returns a list with all the names defined at the top level of the module. In this case, you can say that . __ dict __ holds the namespace of sys and is a concrete representation of the module scope.**

As a further example, suppose that you need to use the name ps1, which is defined in sys. If you know how .__ dict __ and namespaces work in Python, then you can reference ps1 in at least two different ways:

1. Using the dot notation on the module’s name in the form module.name
2. Using a subscription operation on .dict in the form module.dict[‘name’]

Take a look at the following code:
    
    sys.ps1
    '>>> '
     sys.__dict__['ps1']
    '>>> '

### Using the LEGB Rule for Python Scope

__Python resolves names using the so-called LEGB rule, which is named after the Python scope for names. The letters in LEGB stand for Local, Enclosing, Global, and Built-in. Here’s a quick overview of what these terms mean:__

* Local (or function) scope is the code block or body of any Python function or lambda expression. This Python scope contains the names that you define inside the function. These names will only be visible from the code of the function. It’s created at function call, not at function definition, so you’ll have as many different local scopes as function calls. This is true even if you call the same function multiple times, or recursively. Each call will result in a new local scope being created.
* Enclosing (or nonlocal) scope is a special scope that only exists for nested functions. If the local scope is an inner or nested function, then the enclosing scope is the scope of the outer or enclosing function. This scope contains the names that you define in the enclosing function. The names in the enclosing scope are visible from the code of the inner and enclosing functions.
* Global (or module) scope is the top-most scope in a Python program, script, or module. This Python scope contains all of the names that you define at the top level of a program or a module. Names in this Python scope are visible from everywhere in your code.
* Built-in scope is a special Python scope that’s created or loaded whenever you run a script or open an interactive session. This scope contains names such as keywords, functions, exceptions, and other attributes that are built into Python. Names in this Python scope are also available from everywhere in your code. It’s automatically loaded by Python when you run a program or script.


### Functions: The Local Scope

The local scope or function scope is a Python scope created at function calls. Every time you call a function, you’re also creating a new local scope. On the other hand, you can think of each def statement and lambda expression as a blueprint for new local scopes. These local scopes will come into existence whenever you call the function at hand.

**By default, parameters and names that you assign inside a function exist only within the function or local scope associated with the function call. When the function returns, the local scope is destroyed and the names are forgotten. Here’s how this works:**


     def square(base):
    ...     result = base ** 2
    ...     print(f'The square of {base} is: {result}')
    ...
     square(10)
    The square of 10 is: 100
     result  # Isn't accessible from outside square()
    Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
    result
    NameError: name 'result' is not defined
     base  # Isn't accessible from outside square()
    Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
    base
    NameError: name 'base' is not defined
     square(20)
    The square of 20 is: 400


### Nested Functions: The Enclosing Scope

__Enclosing or nonlocal scope is observed when you nest functions inside other functions. The enclosing scope was added in Python 2.2. It takes the form of the local scope of any enclosing function’s local scopes. Names that you define in the enclosing Python scope are commonly known as nonlocal names. Consider the following code:__

     def outer_func():
         # This block is the Local scope of outer_func()
         var = 100  # A nonlocal var
         # It's also the enclosing scope of inner_func()
         def inner_func():
             # This block is the Local scope of inner_func()
             print(f"Printing var from inner_func(): {var}")
    
         inner_func()
         print(f"Printing var from outer_func(): {var}")
    
     outer_func()
    Printing var from inner_func(): 100
    Printing var from outer_func(): 100
     inner_func()
    Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
    NameError: name 'inner_func' is not defined
