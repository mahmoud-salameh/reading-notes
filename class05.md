# React Docs 


__* How would you break a mock into a component heirarchy ? *__
* **Components that appear within another component in the mock should appear as a child in the hierarchy :**



__* What is the single responsibility principle and how does it apply to components ? *__
* single responsibility principle  technique, that is, a component should ideally only do one thing. If it ends up growing, it should be decomposed into smaller subcomponents.*

* *is a computer-programming principle that states that every module, class or function in a computer program should have responsibility over a single part of that program's functionality, and it should encapsulate that part.*

__* What does it mean to build a ‘static’ version of your application ? *__
* static version of your app that renders your data model*

__* Once you have a static application, what do you need to add ? *__
* The original list of products

* The value of the checkbox

* The filtered list of products

__* What are the three questions you can ask to determine if something is state ? *__
* Is it passed in from a parent via props ?

* Does it remain unchanged over time ?

* Can you compute it based on any other state or props in your component ?

__*How can you identify where state needs to live ? *__
* Identify every component that renders something based on that state.


* Either the common owner or another component higher up in the hierarchy should own the state.

* If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.