# Working with forms

An HTML Form is a group of one or more fields/widgets on a web page, which can be used to collect information from users for submission to a server. Forms are a flexible mechanism for collecting user input because there are suitable widgets for entering many different types of data, including text boxes, checkboxes, radio buttons, date pickers and so on. Forms are also a relatively secure way of sharing data with the server, as they allow us to send data in POST requests with cross-site request forgery protection.

![](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Forms/admin_book_add.png)

## HTML Forms

First a brief overview of HTML Forms. Consider a simple HTML form, with a single text field for entering the name of some "team", and its associated label:

![](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Forms/form_example_name_field.png)

The form is defined in HTML as a collection of elements inside <form>...</form> tags, containing at least one input element of type="submit".

    <form action="/team_name_url/" method="post">
        <label for="team_name">Enter name: </label>
        <input id="team_name" type="text" name="name_field" value="Default name for team.">
        <input type="submit" value="OK">
    </form>

## Django form handling process

Django's form handling uses all of the same techniques that we learned about in previous tutorials (for displaying information about our models): the view gets a request, performs any actions required including reading data from the models, then generates and returns an HTML page (from a template, into which we pass a context containing the data to be displayed). What makes things more complicated is that the server also needs to be able to process data provided by the user, and redisplay the page if there are any errors.


![](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Forms/form_handling_-_standard.png)

Based on the diagram above, the main things that Django's form handling does are:

1. Display the default form the first time it is requested by the user. 
    * The form may contain blank fields (e.g. if you're creating a new record), or it may be pre-populated with initial values (e.g. if you are changing a record, or have useful default initial values).
    *     The form is referred to as unbound at this point, because it isn't associated with any user-entered data (though it may have initial values).
2. Receive data from a submit request and bind it to the form. 
    * Binding data to the form means that the user-entered data and any errors are available when we need to redisplay the form.
3. Clean and validate the data. 
    * Cleaning the data performs sanitization of the input (e.g. removing invalid characters that might be used to send malicious content to the server) and converts them into consistent Python types.
    * Validation checks that the values are appropriate for the field (e.g. are in the right date range, aren't too short or too long, etc.)
4. If any data is invalid, re-display the form, this time with any user populated values and error messages for the problem fields.
5. If all data is valid, perform required actions (e.g. save the data, send an email, return the result of a search, upload a file, etc.)
6. Once all actions are complete, redirect the user to another page.
