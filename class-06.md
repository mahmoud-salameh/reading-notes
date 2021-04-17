# *HTML & Javascript*

## *__Chapter 3.FUNCTIONS, METHODS & OBJECTS__*

*__creating an object:literal notation__*

literal notation is the easiest and most populer way to create objects.

when setting properties, treat the values like you would do for variables:strings live in quotes and arrays live in square brackets.


*__accessing an object and dot notation__*

you access the properties or methods of an object using dotnotation.
you can also access properties isong square brackets.


![dot notation or square brackets](https://www.bookofnetwork.com/images/javascript-images/JS_Object-literal---Ways-of-accessing-object-property_04Oct16_1421.png)

To access a property or method of an object you can use the name of the object, followed by a period, then the name of the property or method you want to access(this is known as dot notation).

you can also access the property of an object using square bracket syntax.


This notation is used most commonly used when:

* The name of property is a number.
* A varible is being used in place of the property name.


![dot notation](https://data-flair.training/blogs/wp-content/uploads/sites/2/2019/07/How-to-Create-JavaScript-Objects.jpg)

![dot notation](https://view.publitas.com/42146/346396/pages/8eea6ea8f64e5557051055c621255d97eba8a891-at1000.jpg)




## *__Chapter 5.DOCUMENT OBJECT MODEL__*



![tree](https://devopedia.org/images/article/282/2000.1595439379.jpg)

![tree](https://cdn.javarush.ru/images/article/65608b91-3a7b-4266-834a-a0f65e00c2ec/800.jpeg)

![tree](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5a/DOM-model.svg/1200px-DOM-model.svg.png)




__document object model summary__


* The browser represents the page using a DOM tree. 
* DOM trees have four types of nodes: document nodes,
element nodes, attribute nodes, and text nodes. 
* You can select element nodes by their id or cl ass
attributes, by tag name, or using CSS selector syntax. 
* Whenever a DOM query can return more than one
node, it will always return a Nadel i st. 
* From an element node, you can access and update its
content using properties such as textContent and
i nnerHTML or using DOM manipulation techniques. 
* An element node can contain multiple text nodes and
child elements that are siblings of each other. 
* In older browsers, implementation of the DOM is
inconsistent (and is a popular reason for using jQuery). 
* Browsers offer tools for viewing the DOM tree . 