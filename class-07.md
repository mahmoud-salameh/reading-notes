# HTML

## *__Chapter 15.Layout__*


*__Key Concepts in Positioning Elements__*

__Building Blocks__ 

*Block-level elements
start on a new line*

*Inline elements
flow in between surrounding text*

CSS treats each HTML element as if it is in its own box. This box will either be a block-level box or an inline box.

Block-level boxes start on a new line and act as the main building blocks
of any layout, while inline boxes flow between surrounding text. 

You can control how much space each box takes up by setting the width of the
boxes (and sometimes the height, too). 

To separate boxes, you can use borders, margins, padding, and background colors.

* Normal Flow position:static

* Relative Positioning position:relative

* Absolute Positioning position:absolute

* Fixed Positioning position:fixed

* Floating Elements float

![example for order list](https://image.slidesharecdn.com/web-building-blocks-101028134802-phpapp02/95/web-building-blocks-7-638.jpg?cb=1422618022)

*__Containing Elements__*
If one block-level element sits inside another block-level element then the outer box is known as the containing or parent element.

It is common to group a number of elements together inside a < div>
(or other block-level) element. For example, you might group together
all of the elements that form the header of a site (such as the logo and
the main navigation). 

The < div> element that contains this group of elements is then referred to as the containing element.


![example for order list](https://www.kirupa.com/html5/images/parents_siblings_children_200a.png)


*__Controlling the Position of Elements__* 

__CSS__ has the following positioning schemes that allow you to control the layout of a page: normal flow, relative positioning, and absolute positioning.


You specify the positioning scheme using the position property in CSS. You can also float elements using the float property To indicate where a box should be positioned, you may also need to use box offset properties to tell the browser how far from the top or bottom and left or right it should be placed. 


(You will meet these when we introduce the positioning schemes on the following pages.)


__Screen Sizes__


Different visitors to your site will have different sized screens that show different amounts of information, so your design needs to be able to work on a range of different sized screens.

__Screen Resolution__

Resolution refers to the number of dots a screen shows per inch. 

Some devices have a higher resolution than desktop computers and most
operating systems allow users to adjust the resolution of their screens.



__LAYOUT Summary:__

* < div> elements are often used as containing elements
to group together sections of a page.
* Browsers display pages in normal flow unless you
specify relative, absolute, or fixed positioning.
* The float property moves content to the left or right
of the page and can be used to create multi-column
layouts. (Floated items require a defined width.).
* Pages can be fixed width or liquid (stretchy) layouts.
*  Designers keep pages within 960-1000 pixels wide,
and indicate what the site is about within the top 600
pixels (to demonstrate its relevance without scrolling).
* Grids help create professional and flexible designs.
* CSS Frameworks provide rules for common tasks.
* You can include multiple CSS files in one page.