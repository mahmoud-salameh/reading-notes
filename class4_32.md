# Conditional Rendering

In React, you can create distinct components that encapsulate behavior you need. Then, you can render only some of them, depending on the state of your application.

Conditional rendering in React works the same way conditions work in JavaScript. Use JavaScript operators like if or the conditional operator to create elements representing the current state, and let React update the UI to match them.

Consider these two components:

    function UserGreeting(props) {
    return <h1>Welcome back!</h1>;
    }

    function GuestGreeting(props) {
    return <h1>Please sign up.</h1>;
    }

We’ll create a Greeting component that displays either of these components depending on whether a user is logged in:

    function Greeting(props) {
    const isLoggedIn = props.isLoggedIn;
    if (isLoggedIn) {    return <UserGreeting />;  }  return <GuestGreeting />;}
    ReactDOM.render(
    // Try changing to isLoggedIn={true}:
    <Greeting isLoggedIn={false} />,  document.getElementById('root'));

# Lists and Keys

Given the code below, we use the map() function to take an array of numbers and double their values. We assign the new array returned by map() to the variable doubled and log it:

    const numbers = [1, 2, 3, 4, 5];
    const doubled = numbers.map((number) => number * 2);console.log(doubled);

## Rendering Multiple Components 

You can build collections of elements and include them in JSX using curly braces {}.

Below, we loop through the numbers array using the JavaScript map() function. We return a <li> element for each item. Finally, we assign the resulting array of elements to listItems:

    const numbers = [1, 2, 3, 4, 5];
    const listItems = numbers.map((number) =>  <li>{number}</li>);

We include the entire listItems array inside a <ul> element, and render it to the DOM:

    ReactDOM.render(
    <ul>{listItems}</ul>,  document.getElementById('root')
    );

# Forms

HTML form elements work a bit differently from other DOM elements in React, because form elements naturally keep some internal state. For example, this form in plain HTML accepts a single name:

    <form>
    <label>
        Name:
        <input type="text" name="name" />
    </label>
    <input type="submit" value="Submit" />
    </form>

## Controlled Components

In HTML, form elements such as <input>, <textarea>, and <select> typically maintain their own state and update it based on user input. In React, mutable state is typically kept in the state property of components, and only updated with setState().

For example, if we want to make the previous example log the name when it is submitted, we can write the form as a controlled component:

    class NameForm extends React.Component {
    constructor(props) {
        super(props);
        this.state = {value: ''};
        this.handleChange = this.handleChange.bind(this);
        this.handleSubmit = this.handleSubmit.bind(this);
    }

    handleChange(event) {    this.setState({value: event.target.value});  }
    handleSubmit(event) {
        alert('A name was submitted: ' + this.state.value);
        event.preventDefault();
    }

    render() {
        return (
        <form onSubmit={this.handleSubmit}>        <label>
            Name:
            <input type="text" value={this.state.value} onChange={this.handleChange} />        </label>
            <input type="submit" value="Submit" />
        </form>
        );
    }
    }

# Lifting State Up

Often, several components need to reflect the same changing data. We recommend lifting the shared state up to their closest common ancestor. Let’s see how this works in action.


We will start with a component called BoilingVerdict. It accepts the celsius temperature as a prop, and prints whether it is enough to boil the water:

    function BoilingVerdict(props) {
    if (props.celsius >= 100) {
        return <p>The water would boil.</p>;  }
    return <p>The water would not boil.</p>;}

Additionally, it renders the BoilingVerdict for the current input value.

    class Calculator extends React.Component {
    constructor(props) {
        super(props);
        this.handleChange = this.handleChange.bind(this);
        this.state = {temperature: ''};  }

    handleChange(e) {
        this.setState({temperature: e.target.value});  }

    render() {
        const temperature = this.state.temperature;    return (
        <fieldset>
            <legend>Enter temperature in Celsius:</legend>
            <input          value={temperature}          onChange={this.handleChange} />        <BoilingVerdict          celsius={parseFloat(temperature)} />      </fieldset>
        );
    }
    }

## Adding a Second Input 

Our new requirement is that, in addition to a Celsius input, we provide a Fahrenheit input, and they are kept in sync.

    const scaleNames = {  c: 'Celsius',  f: 'Fahrenheit'};
    class TemperatureInput extends React.Component {
    constructor(props) {
        super(props);
        this.handleChange = this.handleChange.bind(this);
        this.state = {temperature: ''};
    }

    handleChange(e) {
        this.setState({temperature: e.target.value});
    }

    render() {
        const temperature = this.state.temperature;
        const scale = this.props.scale;    return (
        <fieldset>
            <legend>Enter temperature in {scaleNames[scale]}:</legend>        <input value={temperature}
                onChange={this.handleChange} />
        </fieldset>
        );
    }
    }