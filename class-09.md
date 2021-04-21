# JavaScript 


## *__Chapter 10.ERROR HANDLING & DEBUGGING__*

![logo](https://www.yumpu.com/en/image/facebook/5903821.jpg)

__ORDER OF EXECUTION__

To find the source of an error, it helps to know how scripts are processed.
The order in which statements are executed can be complex; some tasks
cannot complete until another statement or function has been run: 

__EXECUTION CONTEXTS__

The JavaScript interpreter uses the concept of execution contexts.
There is one global execution context; plus, each function creates a new
new execution context. They correspond to variable scope. 

__EXECUTION CONTEXT & HOISTING__

Each time a script enters a new execution context, there are two phases
of activity:

1. PREPARE 

* The new scope is created.

* Variables, functions, and arguments are created.

* The value of the this keyword is determined.

2. EXECUTE 

* Now it can assign values to variables 
* Reference functions and run their code
* Execute statements

__UNDERSTANDING ERRORS__

If a JavaScript statement generates an error, then it throws an exception.
At that point, the interpreter stops and looks for exception-handl ing code. 

If you are anticipating that something in your code
may cause an error, you can use a set of statements
to handle the error This is important because if the error is not handled,
the script will just stop processing and the user will
not know why. So exception-handling code should
inform users when there is a problem. 

__ERROR OBJECTS__

Error objects can help you find where your *__mistakes are
and browsers have tools to help you read them. __*

When an Er ror object is created, it will contain the
following properties: 

|PROPERTY| DESCRIPTION|
|------|-------|
|message|Description|
|file Number|Name of the JavaScript file|
|line Number|Type of execution|

When there is an error, you can see all of this
information in the __JavaScript console / Error console
of the browser.__


__ERROR OBJECTS CONTINUED __

Syntax Error
__SYNTAX IS NOT CORRECT__
This is caused by incorrect use of the rules of the
language. It is often the result of a simple typo. 

MISMATCHING OR UNCLOSED QUOTES

SyntaxError: Unexpect ed EOF

Ref erenceError
__VARIABLE DOES NOT EXIST__
This is caused by a variable that is not declared or is
out of scope. 

**ReferenceError: Can't find variable: *name of the variable*


These two pages show JavaScript's seven different types of error objects
and some common examples of the kinds of errors you are likely to see.
As you can tell, the errors shown by the browsers can be rather cryptic.

Type Error
__VALUE IS UNEXPECTED DATA TYPE__
This is often caused by trying to use an object or
method that does not exist

INCORRECT CASE FOR document OBJECT
l!Jocument.wri te ('Oops! ');


You can handle errors gracefully using try, catch,
throw, and finaily statements.


__ERROR HANDLING & DEBUGGING SUMMARY__

* If you understand execution contexts (which have two
stages) and stacks, you are more likely to find the error
in your code. 

* Debugging is the process of finding errors. It involves a
process of deduction. 

* The console helps narrow down the area in which the
error is located, so you can try to find the exact error. 
* JavaScript has 7 different types of errors. Each creates
its own error object, which can tell you its line number
and gives a description of the error. 
* If you know that you may get an error, you can handle
it gracefully using the try, catch, finally statements.
Use them to give your users helpful feedback. 
