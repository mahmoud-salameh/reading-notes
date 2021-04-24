# HTML


## *__Chapter 16.Images__*

__Controlling sizes of images in CSS__

You can control the size of an image using the width and height properties in CSS, just like you can for any other box.

![example of img](https://css-tricks.com/wp-content/uploads/2014/05/sizes-attribute1.svg)

First you need to determine the sizes of images that will be used commonly throughout the site, then give each size a name.

For example:
* small
* medium
* large

Where the < img> elements appear in the HTML, rather than using width and height attributes you can use these names as values for the class attribute.

In the CSS, you add selectors for each of the class names, then use the CSS width and height properties to control the image dimensions.

__Aligning  images Using CSS__

In the last chapter, you saw how the float property can be used to move an element to the left or the right of its containing block, allowing text to flow around it.

Example:

1. 
img {
  border: 1px solid #ddd;
  border-radius: 4px;
  padding: 5px;
  width: 150px;
}
2. 
img {
  max-width: 100%;
  height: auto;
}

3. 
img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}



__IMAGES Summary:__
* You can specify the dimensions of images using CSS.
This is very helpful when you use the same sized
images on several pages of your site.
* Images can be aligned both horizontally and vertically
using CSS.
* You can use a background image behind the box
created by any element on a page.
* Background images can appear just once or be
repeated across the background of the box.
* You can create image rollover effects by moving the
background position of an image.
* To reduce the number of images your browser has to
load, you can create image sprites.


## *__Chapter 19.Practical Information__*

*__On-Page SEO__*

In every page of your website there are seven key places where keywords (the words people might search on to find your site) can appear in order to improve its findability.

1: Page Title The page title appears at the top of the browser window or on the tab of a browser. 
It is specified in the < title> element which lives inside the < head> element.

2: URL / Web Address The name of the file is part of the URL. 
Where possible, use keywords in the file name.

3: Headings If the keywords are in a heading < hn> element then a search engine will know that this page is all about that subject and give it greater weight than other text.

4: Text Where possible, it helps to repeat the keywords in the main body of the text at least 2-3 times. Do not, however, over-use these terms, because the text must be easy for a human to read.

5: Link Text Use keywords in the text that create links between pages (rather than using generic expressions such as "click here").

6: Image Alt Text Search engines rely on you providing accurate descriptionsof images in the alt text. 
This will also help your images show up in the results of image-based searches.


7: Page Descriptions The description also lives insidethe < head> element and is specified using a < meta> tag.
It should be a sentence that describes the content of the page.

__Analytics: Learning about your Visitors__


As soon as people start coming to your site, you can start analyzing
how they found it, what they were looking at and at what point they are
leaving. One of the best tools for doing this is a free service offered by
Google called Google Analytics.

__PRACTICAL INFORMATION Summary:__

* Search engine optimization helps visitors find your
sites when using search engines.
* Analytics tools such as Google Analytics allow you to
see how many people visit your site, how they find it,
and what they do when they get there.
* To put your site on the web, you will need to obtain a
domain name and web hosting.
* FTP programs allow you to transfer files from your
local computer to your web server.
* Many companies provide platforms for blogging, email
newsletters, e-commerce and other popular website
tools (to save you writing them from scratch).