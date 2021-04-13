# HTML & Javascript

## *__Chapter 4. HTML Links__*

*__Writing Links__*

Links are created using the < a> element. Users can click on anything
between the opening < a> tag and the closing < /a> tag. You specify
which page you want to link to using the href attribute.

![links](https://d2h0cx97tjks2p.cloudfront.net/blogs/wp-content/uploads/sites/2/2020/06/Links-in-HTML.jpg)


*LINKS Summary:*

* Links are created using the < a> element.
* The < a> element uses the href attribute to indicate
the page you are linking to.
* If you are linking to a page within your own site, it is
best to use relative links rather than qualified URLs.
* You can create links to open email programs with an
email address in the "to" field.
* You can use the id attribute to target elements within
a page that can be linked to.


## *__Chapter 15.Layout__*


*__Key Concepts in Positioning Elements__*

Building Blocks
CSS treats each HTML element as if it is in its
own box. This box will either be a block-level
box or an inline box.
Block-level boxes start on a new line and act as the main building blocks
of any layout, while inline boxes flow between surrounding text. You can
control how much space each box takes up by setting the width of the
boxes (and sometimes the height, too). To separate boxes, you can use
borders, margins, padding, and background colors


![example for order list](https://image.slidesharecdn.com/web-building-blocks-101028134802-phpapp02/95/web-building-blocks-7-638.jpg?cb=1422618022)

*__Containing Elements__*
If one block-level element sits inside another
block-level element then the outer box is
known as the containing or parent element.
It is common to group a number of elements together inside a <div>
(or other block-level) element. For example, you might group together
all of the elements that form the header of a site (such as the logo and
the main navigation). The <div> element that contains this group of
elements is then referred to as the containing element.


![example for order list](https://www.kirupa.com/html5/images/parents_siblings_children_200a.png)


*__Controlling the Position of Elements__* 

CSS has the following positioning schemes that allow you to control the layout of a page: normal flow, relative positioning, and absolute positioning. 
You specify the positioning scheme using the position property in CSS. You can also float elements using the float property


To indicate where a box should be positioned, you may also need to use box offset properties to tell the browser how far from the top or bottom and left or right it should be placed. 
(You will meet these when we introduce the positioning schemes on the following pages.)


__Screen Sizes__


Different visitors to your site will have different sized screens that show
different amounts of information, so your design needs to be able to
work on a range of different sized screens.

__Screen Resolution__

Resolution refers to the number of dots a screen shows per inch. Some
devices have a higher resolution than desktop computers and most
operating systems allow users to adjust the resolution of their screens.



*LAYOUT Summary:*

* < div> elements are often used as containing elements
to group together sections of a page.
* Browsers display pages in normal flow unless you
specify relative, absolute, or fixed positioning.
* The float property moves content to the left or right
of the page and can be used to create multi-column
layouts. (Floated items require a defined width.)
* Pages can be fixed width or liquid (stretchy) layouts.
*  Designers keep pages within 960-1000 pixels wide,
and indicate what the site is about within the top 600
pixels (to demonstrate its relevance without scrolling).
* Grids help create professional and flexible designs.
* CSS Frameworks provide rules for common tasks.
* You can include multiple CSS files in one page.


## *__JAVASCRIPT Chapter 3.Listst__*

*__LISTS Summary:__*

* There are three types of HTML lists: ordered,
unordered, and definition.
* Ordered lists use numbers.
* Unordered lists use bullets.
* Definition lists are used to define terminology.
* Lists can be nested inside one another.


### *__6 Reasons for Pair Programming__*


Why pair program?
While learning to code, developers likely study several programming languages Similar to a foreign language class, there are four fundamental skills that help anyone learn a new language: Listening: hearing and interpreting the vocabulary Speaking: using the correct words to communicate an idea Reading: understanding what written language intends to convey Writing: producing from scratch a meaningful



1. Greater efficiency
It is a common misconception that pair programming takes a lot longer and is less efficient. In reality, when two people focus on the same code base, it is easier to catch mistakes in the making.

2. Engaged collaboration
When two programmers focus on the same code, the experience is more engaging and both programmers are more focused than if they were working alone.
It is harder to procrastinate or get off track when someone else is relying on you to complete the work.

3. Learning from fellow students
Everyone has a different approach to problem solving; working with a teammate can expose developers to techniques they otherwise would not have thought of. 
If one developer has a unique approach to a specific problem, pair programming exposes the other developer to a new solution.

4. Social skills
Pair programming is great for improving social skills. When working with someone who has a different coding style, communication is key. 
This can become more difficult when two programmers have different personalities.
Pair programming not only improves programming skills, but can also help programmers develop their interpersonal skills.

5. Job interview readiness
A common step in many interview processes involves pair programming between a current employee and an applicant, either in person or through a shared screen. 
They will carry out exercises together, such as code challenges, building a project or feature, or debugging an existing code base.

6. Work environment readiness
Many companies that utilize pair programing expect to train fresh hires from CS-degree programs on how they operate to actually deliver a product. 
Code Fellows graduates who are already familiar with how pairing works can hit the ground running at a new job, with one less hurdle to overcome.

