## Chart.js
__EASILY CREATE STUNNING ANIMATED CHARTS WITH CHART.JS__

Charts are far better for displaying data visually than tables and have the added benefit that no one is ever going to press-gang them into use as a layout tool. 
They’re easier to look at and convey data quickly, but they’re not always easy to create.

A great way to get started with [chart.js](https://www.chartjs.org/) is with Chart.js, a JavaScript plugin that uses HTML5’s canvas element to draw the graph onto the page. 
It’s a well documented plugin that makes using all kinds of bar charts, line charts, pie charts and more, incredibly easy.

To see how to use chart.js we’re going to create a set of 3 graphs; one will show the number of buyers a fictional product has over the course of 6 months, this will be a line chart; the second will show which countries the customers come from, this will be the pie chart; finally we’ll use a bar chart to show profit over the period.


*__Installation:__*

You can get the latest version of Chart.js from [npm](https://www.npmjs.com/package/chart.js) , the [GitHub releases](https://github.com/chartjs/Chart.js/releases/tag/v3.2.0) , or use a [Chart.js CDN](https://www.jsdelivr.com/package/npm/chart.js) . Detailed installation instructions can be found on the [installation](https://www.chartjs.org/docs/latest/getting-started/installation.html) page.


*__Contributing__*

Before submitting an issue or a pull request to the project, please take a moment to look over the [contributing guidelines](https://www.chartjs.org/docs/latest/developers/contributing.html) first.

__The < canvas> element__

At first sight a < canvas> looks like the < img> element, with the only clear difference being that it doesn't have the src and alt attributes. 
Indeed, the < canvas> element has only two attributes, width and height. 
These are both optional and can also be set using DOM properties. 
When no width and height attributes are specified, the canvas will initially be 300 pixels wide and 150 pixels high. 
The element can be sized arbitrarily by CSS, but during rendering the image is scaled to fit its layout size: if the CSS sizing doesn't respect the ratio of the initial canvas, it will appear distorted.

__Drawing shapes with canvas__

Now that we have set up our [canvas environment](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Basic_usage), we can get into the details of how to draw on the canvas. By the end of this article, you will have learned how to draw rectangles, triangles, lines, arcs and curves, providing familiarity with some of the basic shapes. 
Working with paths is essential when drawing objects onto the canvas and we will see how that can be done.

__The grid__

Before we can start drawing, we need to talk about the canvas grid or coordinate space. 
Our HTML skeleton from the previous page had a canvas element 150 pixels wide and 150 pixels high. 
To the right, you see this canvas with the default grid overlayed. 
Normally 1 unit in the grid corresponds to 1 pixel on the canvas. 
The origin of this grid is positioned in the top left corner at coordinate (0,0). 
All elements are placed relative to this origin. So the position of the top left corner of the blue square becomes x pixels from the left and y pixels from the top, at coordinate (x,y). 
Later in this tutorial we'll see how we can translate the origin to a different position, rotate the grid and even scale it, but for now we'll stick to the default.

