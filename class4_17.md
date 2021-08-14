# How to Web Scrape with Python

## Web Scraping

Web scraping is a technique to automatically access and extract large amounts of information from a website, which can save a huge amount of time and effort. In this article, we will go through an easy example of how to automate downloading hundreds of files from the New York MTA. This is a great exercise for web scraping beginners who are looking to understand how to web scrape. Web scraping can be slightly intimidating, so this tutorial will break down the process of how to go about the process.

### New York MTA Data
We will be downloading turnstile data from this site:
    
    http://web.mta.info/developers/turnstile.html

Turnstile data is compiled every week from May 2010 to present, so hundreds of .txt files exist on the site. Below is a snippet of what some of the data looks like. Each date is a link to the .txt file that you can download.

![](https://miro.medium.com/max/233/1*5Hwlx8IZxJ0m7AIx0TnddA.png)

### Inspecting the Website

The first thing that we need to do is to figure out where we can locate the links to the files we want to download inside the multiple levels of HTML tags. Simply put, there is a lot of code on a website page and we want to find the relevant pieces of code that contains our data. If you are not familiar with HTML tags, refer to W3Schools Tutorials. It is important to understand the basics of HTML in order to successfully web scrape.

On the website, right click and click on “Inspect”. This allows you to see the raw code behind the site.

![](https://miro.medium.com/max/193/1*IYaJ73s529Dtb94xDemFcQ.png)

Once you’ve clicked on “Inspect”, you should see this console pop up.

![](https://miro.medium.com/max/700/1*rcQ4KRlp1fhMFUydVv5lMg.png)

Notice that on the top left of the console, there is an arrow symbol.

If you click on this arrow and then click on an area of the site itself, the code for that particular item will be highlighted in the console. I’ve clicked on the very first data file, Saturday, September 22, 2018 and the console has highlighted in blue the link to that particular file.

    <a href=”data/nyct/turnstile/turnstile_180922.txt”>Saturday, September 22, 2018</a>


### Python Code

We start by importing the following libraries.

    import requests
    import urllib.request
    import time
    from bs4 import BeautifulSoup


If the access was successful, you should see the following output:

![](https://miro.medium.com/max/414/1*fyqRGzG8IbhhjxF2Q5MU_Q.png)


Next we parse the html with BeautifulSoup so that we can work with a nicer, nested BeautifulSoup data structure. If you are interested in learning more about this library, check out the BeatifulSoup documentation.

    soup = BeautifulSoup(response.text, “html.parser”)

We use the method .findAll to locate all of our <a> tags.

    soup.findAll('a')

This code gives us every line of code that has an <a> tag. The information that we are interested in starts on line 38 as seen below. That is, the very first text file is located in line 38, so we want to grab the rest of the text files located below.

![](https://miro.medium.com/max/582/1*G6YulYb5rczkVvmn7nbQ6g.png)

