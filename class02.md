# class02

# React lifecycle 

![lifecycle](https://res.cloudinary.com/practicaldev/image/fetch/s--RrkCw0QH--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/di74f0jivvxwhelmqhof.png) 

Based off the diagram, what happens first, the ‘render’ or the componentDidMount ? 
__Based off the diagram the ‘render’ happens before the  ‘componentDidMount’.__

 What is the very first thing to happen in the lifecycle of React ? 
Render phase 

 Put the following things in the order that they happen: componentDidMount, render, constructor, componentWillUnmount, React Updates :- 
*  Constructor.
* Render.
*  React Updates. 
* ComponentDidMount. 
* ComponentWillUnmount.

What does componentDidMount do ?
This method is invoked immediately after a component is mounted. If you need to load anything using a network request or initialize the DOM, it should go here. This method is a good place to set up any subscriptions.




What types of things can you pass in the props ?
__Props are pass into the component.__


What is the big difference between props and state ?
* Props pass into a component. 

* Props is handled outside of that component.

* Props is update it outside the component.

* State is handled inside of that component.

* State is update it inside the component.

When do we re-render our application ?
Based on something the user has done.  
What are some examples of things that we could store in state ? 
**Based on user input :**

* Input Elements. 
![first](https://documentation.logianalytics.com/logiinfov11/content/resources/images/workingui_01a.gif)

* Check Box. 
![second](https://static9.depositphotos.com/1674252/1149/v/600/depositphotos_11495891-stock-illustration-check-marks.jpg)

* Select Box.
![third](https://i0.wp.com/www.cssscript.com/wp-content/uploads/2021/01/High-Performance-Select-Box-JavaScript-Library-Virtual-Select.png?fit=563%2C391&ssl=1)