# Understanding the JavaScript Call Stack

## What is a ‘call’ ?

**The call stack is primarily used for function invocation (call). Since the call stack is single, function(s) execution, is done, one at a time, from top to bottom. It means the call stack is synchronous.** 

## How many ‘calls’ can happen at once ? 

**It is single-threaded. Meaning it can only do one thing at a time.** 

## What does LIFO mean ?

**When we say that the call stack, operates by the data structure principle of Last In, First Out, it means that the last function that gets pushed into the stack is the first to be pop out, when the function returns.**  

## Draw an example of a call stack and the functions that would need to be invoked to generate that call stack. 
 function firstFunction(){
console.log("Hello from firstFunction");
    }
   function secondFunction(){
firstFunction();
console.log("The end from secondFunction");
    }
    secondFunction(); 


## What causes a Stack Overflow ? 

**A stack overflow occurs when there is a recursive function (a function that calls itself) without an exit point. The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error.** 

# JavaScript error messages 

## What is a ‘refrence error’ ? 

__*use a variable that is not yet declared *__ 

**This is also a common thing when using const and let, they are hoisted like var and function but there is a time between the hoisting and being declared so when you try to access them a reference error occurs, the fact that this happens to let and const is called Temporal Dead Zone (TDZ).** 

## What is a ‘syntax error’ ? 

**this occurs when you have something that cannot be parsed in terms of syntax** 

**Some syntax errors like sending a trailing comma when calling a function are handled without error by most recent browsers, but older ones you have to be careful.**  

## What is a ‘range error’ ?

**An array for instance cannot have a negative length** 
**I prefer not to mutate my variables whenever possible (making them constants and not variables) but this is a method that is available and now you know it.**

## What is a ‘tyep error’ ?

**this types of errors show up when the types (number, string and so on) you are trying to use or access are incompatible** 

**There are also warnings, for instance telling you about a deprecated method, which can be found more frequently in firefox developer tools.** 

## What is a breakpoint ? 

**The breakpoint can also be achieved by putting a debugger statement in your code in the line you want to break.** 

## What does the word ‘debugger’ do in your code ?

**its to simply console.log() the variables you want to check or, by using chrome developer tools**