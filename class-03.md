# HTML & Javascript

## *__Chapter 3.HTML Lists__*

__Ordered Lists:__
The ordered list is created with the < ol> element.

Each item in the list is placed between an opening < li> tag and a closing < /li> tag. (The li stands for list item.)

Unordered Lists

The unordered list is created with the < ul> element.

Each item in the list is placed between an opening < li> tag and a closing < /li> tag. (The li stands for list item.)

LIST Summary:

* There are three types of HTML lists: ordered, unordered, and definition.
* Ordered lists use numbers.
* Unordered lists use bullets.
* Definition lists are used to define terminology.
* Lists can be nested inside one another.

![example for order list](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQVzFVP48nXjL1X9SxBDWRIVCh3yEmam-9wXw&usqp=CAU)

![example for order list](https://i0.wp.com/www.tutorialbrain.com/wp-content/uploads/2019/01/Unordered-List.jpg?fit=474%2C397&ssl=1&is-pending-load=1)

## *__Chapter 13.Boxes__*

__Border, Margin & Padding__

Every box has three available properties that can be adjusted to control its appearance:
1- Border Every box has a border (even if it is not visible or is specified to be 0 pixels wide). The border separates the edge of one box from another.

2- Margin Margins sit outside the edge of the border. You can set the width of a margin to create a gap between the borders of two adjacent boxes.

3-PaddingPadding is the space betweenthe border of a box and any content contained within it. Adding padding can increase the readability of its contents.


![example for order list](https://sabe.io/classes/css/css-box-model-padding-border-margin/css-box-model.png)

BOXES Summary:

* CSS treats each HTML element as if it has its own box.
* You can use CSS to control the dimensions of a box.
* You can also control the borders, margin and padding
for each box with CSS.
* It is possible to hide elements using the display and
visibility properties.
* Block-level boxes can be made into inline boxes, and
inline boxes made into block-level boxes.
* Legibility can be improved by controlling the width of
boxes containing text and the leading.
* CSS3 has introduced the ability to create image
borders and rounded borders.


## *__JAVASCRIPT__*

![javascript logo](https://www.oreilly.com/library/view/javascript-and-jquery/9781118531648/images/p055-001.jpg)

## *__Chapter 2. BASIC JAVASCRIPT INSTRUCTIONS__*

An array is a special type of variable. It doesn't just store one value; it stores a list of values.  

You should consider using an array whenever you are working with a list or a set of values that are related to each other.
 Arrays are especially helpful when you do not know how many items a list will contain because, when you create the array, you do not need to specify how many values it will hold.
  If you don't know how many items a list will contain, rather than creating enough variables for a long list (when you might only use a small percentage of them), using an array is considered a better solution For example, an array can be suited to storing the individual items on a shopping list because it is a list of related items. Additionally, each time you write a new shopping list, the number of items on it may differ.

 As you will see on the next page, values in an array are separated by commas. In Chapter 12, you will see that arrays can be very helpful when representing complex data.

NUMBERING ITEMS IN AN ARRAY  Each item in an array is automatically given a number called an index. This can be used to access specific items in the array. Consider the following array which holds three colors:

Confusingly, index values start at 0 (not 1), so the following table shows items from the array and their corresponding index values:


## *__Chapter 4. DECISIONS & LOOPS __*


*__USING IF ... ELSE STATEMENTS*__

Here you can see that anif ... e 1 se statement allows you to provide two sets of code:
1. one set if the condition evaluates to true.
2. another set if the condition is false.

In this test, there are two possible outcomes: a user can either get a score equal to or greater than the pass mark (which means they pass), or they can score less than the pass mark (which means they fail).

One response is required for each eventuality. The response is then written to the page.

Note that the statements inside an if statement should be followed by a semicolon, but there is no need to place one after the closing curly brace of the code blocks. 

*__SWITCH STATEMENTS__*

A switch statement starts with a variable called the switch value.

Each case indicates a possible value for this variable and the code that should run if the variable matches that value.

Here, the variable named 1 eve l is the switch value.
If the value of the l eve 1 variable is the string One, then the code for the first case is executed. 

If it is Two, the second case is executed. If it is Three, the third case is executed. If it is none of these, the code for the defaul t case is executed.
The entire statement lives in one code block (set of curly braces), and a colon separates the option from the statements that are to be run if the case matches the switch value.

At the end of each case is the break keyword. 

It tells the JavaScript interpreter that it has finished with this switch statement and to proceed to run any subsequent code that appears after it.



![loops](https://data-flair.training/blogs/wp-content/uploads/sites/2/2019/07/JavaScript-Loops-1200x720.jpg)


![loops exmp](https://cdn.programiz.com/sites/tutorial2program/files/java-if-else-if-statement.png)

![loops exmp](https://www.devopsschool.com/blog/wp-content/uploads/2020/07/JavaScript-Logical-Operator.png)