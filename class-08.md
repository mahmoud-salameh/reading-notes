# HTML

## *__Chapter 7.Forms__*

*__How Forms Work__*
A user fills in a form and then presses a button to submit the information to the server.

The name of each form control is sent to the server along with the value the user enters or selects.

The server processes the information using a programming language such as PHP, C#, VB.net, or Java. 
It may also store the information in a database.

The server creates a new page to send back to the browser based on the information received.

A form may have several form controls, each gathering different information. 
The server needs to know which piece of inputted data corresponds with which form element.

To differentiate between various pieces of inputted data, information is sent from the browser to the server using name/value pairs. 
In this example, the form asks for the visitor's username and also for their favorite jazz musician. The name/value pairs sent to the server are:

If the form control allows the user to enter text, then the value of the form control is whatever the user has typed in.

If the form control allows you to choose from a fixed set of answers (e.g. radio buttons, checkboxes or a drop down list), the web page author will add code that gives each option an automatic value.

![example of forms](https://www.htmlgoodies.com/img/2010/06/HTML-Forms-From-Basics-to-Style-Layouts-Figure2.gif)


![example of forms](https://i.ytimg.com/vi/NfmB5Q4U1sk/maxresdefault.jpg)


__FORMS Summary:__

* Whenever you want to collect information from
visitors you will need a form, which lives inside a
<form> element.
* Information from a form is sent in name/value pairs.
* Each form control is given a name, and the text the
user types in or the values of the options they select
are sent to the server.
* HTML5 introduces new form elements which make it
easier for visitors to fill in forms.



## *__Chapter 14.Lists, Tables & Forms__*

![example of forms](https://slideplayer.com/slide/13207759/79/images/3/Ordered+List+%3COL%3E+%E2%80%A6..+%3C%2FOL%3E+Drink+Tea+Coffee+Fruits+Apple.jpg)


![example of forms](https://images.slideplayer.com/24/7397420/slides/slide_21.jpg)

![example of forms](https://farm5.staticflickr.com/4684/39512922541_f0269644ac_o.png)


__LISTS, TABLES AND FORM Summary:__

X In addition to the CSS properties covered in other
chapters which work with the contents of all elements,
there are several others that are specifically used to
control the appearance of lists, tables, and forms.
X List markers can be given different appearances
using the list-style-type and list-style image
properties.
X Table cells can have different borders and spacing in
different browsers, but there are properties you can
use to control them and make them more consistent.
X Forms are easier to use if the form controls are
vertically aligned using CSS.
X Forms benefit from styles that make them feel more
interactive.




# JavaScript 


## *__Chapter 6.Events__*

HTML events are "things" that happen to HTML elements.

When JavaScript is used in HTML pages, JavaScript can "react" on these events.


*__What can JavaScript Do?__*

* Things that should be done every time a page loads
* Things that should be done when the page is closed
* Action that should be performed when a user clicks a button
* Content that should be verified when a user inputs data
And more ...
Many different methods can be used to let JavaScript work with events:

* HTML event attributes can execute JavaScript code directly
* HTML event attributes can call JavaScript functions
* You can assign your own event handler functions to HTML elements
* You can prevent events from being sent or being handled
And more


![example of forms](https://data-flair.training/blogs/wp-content/uploads/sites/2/2019/07/Ways-of-Using-JavaScript-Events-1200x720.png)

_EVENTS SUMMARY:__

* Events are the browser's way of indicating whensomething has happened (such as when a page has finished loading or a button has been clicked). 

* Binding is the process of stating which event you are waiting to happen, and which element you are waiting for that event to happen upon.

* When an event occurs on an element, it can trigger a JavaScript function. When this function then changes the web page in some way, it feels interactive because it has responded to the user. 

* You can use event delegation to monitor for events that happen on all of the children of an element. 

* The most commonly used events are W3C DOM events, although there are others in the HTMLS specification as well as browser-specific events. 
