# React

React (also known as React.js or ReactJS) is a free and open-source front-end JavaScript library for building user interfaces or UI components. It is maintained by Facebook and a community of individual developers and companies.React can be used as a base in the development of single-page or mobile applications. However, React is only concerned with state management and rendering that state to the DOM, so creating React applications usually requires the use of additional libraries for routing, as well as certain client-side functionality.

## Introducing JSX

It is called JSX, and it is a syntax extension to JavaScript. We recommend using it with React to describe what the UI should look like. JSX may remind you of a template language, but it comes with the full power of JavaScript.

## Why JSX? 

React embraces the fact that rendering logic is inherently coupled with other UI logic: how events are handled, how the state changes over time, and how the data is prepared for display.

Instead of artificially separating technologies by putting markup and logic in separate files, React separates concerns with loosely coupled units called “components” that contain both. We will come back to components in a further section, but if you’re not yet comfortable putting markup in JS, this talk might convince you otherwise.

## Embedding Expressions in JSX 

In the example below, we declare a variable called name and then use it inside JSX by wrapping it in curly braces:

    const name = 'Josh Perez';const element = <h1>Hello, {name}</h1>;
    ReactDOM.render(
    element,
    document.getElementById('root')
    );

## JSX is an Expression Too 

After compilation, JSX expressions become regular JavaScript function calls and evaluate to JavaScript objects.

This means that you can use JSX inside of if statements and for loops, assign it to variables, accept it as arguments, and return it from functions:

    function getGreeting(user) {
    if (user) {
        return <h1>Hello, {formatName(user)}!</h1>;  }
    return <h1>Hello, Stranger.</h1>;}

## Rendering Elements

An element describes what you want to see on the screen:

    const element = <h1>Hello, world</h1>;
## Rendering an Element into the DOM 

Let’s say there is a <div> somewhere in your HTML file:

    <div id="root"></div>


## Updating the Rendered Element 

React elements are immutable. Once you create an element, you can’t change its children or attributes. An element is like a single frame in a movie: it represents the UI at a certain point in time.

Consider this ticking clock example:



    function tick() {
    const element = (
        <div>
        <h1>Hello, world!</h1>
        <h2>It is {new Date().toLocaleTimeString()}.</h2>
        </div>
    );
    ReactDOM.render(element, document.getElementById('root'));}

    setInterval(tick, 1000);

## React Only Updates What’s Necessary 

React DOM compares the element and its children to the previous one, and only applies the DOM updates necessary to bring the DOM to the desired state.

You can verify by inspecting the last example with the browser tools:

![](https://reactjs.org/c158617ed7cc0eac8f58330e49e48224/granular-dom-updates.gif)

Even though we create an element describing the whole UI tree on every tick, only the text node whose contents have changed gets updated by React DOM.