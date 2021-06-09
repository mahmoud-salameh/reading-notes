# Controlled Components

n HTML, form elements such as < input>, < textarea>, and < select> typically maintain their own state and update it based on user input. 

In React, mutable state is typically kept in the state property of components, and only updated with setState().

We can combine the two by making the React state be the “single source of truth”. 

Then the React component that renders a form also controls what happens in that form on subsequent user input. 

An input form element whose value is controlled by React in this way is called a “controlled component”.

It can sometimes be tedious to use controlled components, because you need to write an event handler for every way your data can change and pipe all of the input state through a React component. This can become particularly annoying when you are converting a preexisting codebase to React, or integrating a React application with a non-React library. In these situations, you might want to check out uncontrolled components, an alternative technique for implementing input forms.





1. The condition is what you’re actually testing. The result of your condition should be true or false or at least coerce to either boolean value.

2. A ? separates our conditional from our true value. Anything between the ? and the : is what is executed if the condition evaluates to true.
3. Finally a : colon. If your condition evaluates to false, any code after the colon is executed.

