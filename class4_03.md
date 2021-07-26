#  FileIO & Exceptions

## What Is a File?

**Before we can go into how to work with files in Python, it’s important to understand what exactly a file is and how modern operating systems handle some of their aspects.**

__At its core, a file is a contiguous set of bytes [used to store data](https://en.wikipedia.org/wiki/Computer_file). This data is organized in a specific format and can be anything as simple as a text file or as complicated as a program executable. In the end, these byte files are then translated into binary 1 and 0 for easier processing by the computer.__
### Files on most modern file systems are composed of three main parts:

1.__**Header**__: metadata about the contents of the file (file name, size, type, and so on)
2.__**Data**__: contents of the file as written by the creator or editor
3.__**End of file (EOF)**__: special character that indicates the end of the file

![h-d-e](https://files.realpython.com/media/FileFormat.02335d06829d.png)
### File Paths
__**When you access a file on an operating system, a file path is required. The file path is a string that represents the location of a file. It’s broken up into three major parts:**__
1.__**Folder Path**__: the file folder location on the file system where subsequent folders are separated by a forward slash / (Unix) or backslash \ (Windows)
2._**File Name_**__: the actual name of the file
3.__**Extension**__: the end of the file path pre-pended with a period (.) used to indicate the file type

__**Here’s a quick example. Let’s say you have a file located within a file structure like this:**__

    /
    │
    ├── path/
    |   │
    │   ├── to/
    │   │   └── cats.gif
    │   │
    │   └── dog_breeds.txt
    |
    └── animals.csv

    Let’s say you wanted to access the cats.gif file, and your current location was in the same folder as path. In order to access the file, you need to go through the path folder and then the to folder, finally arriving at the cats.gif file. The Folder Path is path/to/. The File Name is cats. The File Extension is .gif. So the full path is path/to/cats.gif.

## Opening and Closing a File in Python

When you want to work with a file, the first thing to do is to open it. This is done by invoking the open() built-in function. open() has a single required argument that is the path to the file. open() has a single return, the file object:

    file = open('dog_breeds.txt')

    After you open a file, the next thing to learn is how to close it.

It’s important to remember that it’s your responsibility to close the file. In most cases, upon termination of an application or script, a file will be closed eventually. However, there is no guarantee when exactly that will happen. This can lead to unwanted behavior including resource leaks. It’s also a best practice within Python (Pythonic) to make sure that your code behaves in a way that is well defined and reduces any unwanted behavior.

When you’re manipulating a file, there are two ways that you can use to ensure that a file is closed properly, even when encountering an error. The first way to close a file is to use the try-finally block:

    reader = open('dog_breeds.txt')
    try:
    # Further file processing goes here
    finally:
    reader.close()

Other options for modes are fully documented online, but the most commonly used ones are the following:

|Character | Meaning|
|---|---|
|'r'|Open for reading (default)|
|'w'|Open for writing, truncating (overwriting) the file first|
|'rb' or 'wb'|Open in binary mode (read/write using byte data)|

There are three different categories of file objects:
* Text files
* Buffered binary files
* Raw binary files

## Reading and Writing Opened Files
__Once you’ve opened up a file, you’ll want to read or write to the file. First off, let’s cover reading a file. There are multiple methods that can be called on a file object to help you out:__

|Method | What It Does|
|---|---|
|.read(size=-1)|This reads from the file based on the number of size bytes. If no argument is passed or None or -1 is passed, then the entire file is read.|
|.readline(size=-1)|This reads at most size number of characters from the line. This continues to the end of the line and then wraps back around. If no argument is passed or None or -1 is passed, then the entire line (or rest of the line) is read.|
|.readlines()|This reads the remaining lines from the file object and returns them as a list.|

Using the same dog_breeds.txt file you used above, let’s go through some examples of how to use these methods. Here’s an example of how to open and read the entire file using .read():

    >>> with open('dog_breeds.txt', 'r') as reader:
    >>>     # Read & print the entire file
    >>>     print(reader.read())
    Pug
    Jack Russell Terrier
    English Springer Spaniel
    German Shepherd
    Staffordshire Bull Terrier
    Cavalier King Charles Spaniel
    Golden Retriever
    West Highland White Terrier
    Boxer
    Border Terrier

# Python Exceptions: An Introduction

__A Python program terminates as soon as it encounters an error. In Python, an error can be a syntax error or an exception. In this article, you will see what an exception is and how it differs from a syntax error. After that, you will learn about raising exceptions and making assertions. Then, you’ll finish with a demonstration of the try and except block.__
![py](https://files.realpython.com/media/intro.8915db1758d8.png)
## Exceptions versus Syntax Errors

__Syntax errors occur when the parser detects an incorrect statement. Observe the following example:__

    >>> print( 0 / 0 ))
    File "<stdin>", line 1
    print( 0 / 0 ))
                  ^
    SyntaxError: invalid syntax

This time, you ran into an exception error. This type of error occurs whenever syntactically correct Python code results in an error. The last line of the message indicated what type of exception error you ran into.

## The AssertionError Exception
Instead of waiting for a program to crash midway, you can also start by making an assertion in Python. We assert that a certain condition is met. If this condition turns out to be True, then that is excellent! The program can continue. If the condition turns out to be False, you can have the program throw an AssertionError exception.
![asset](https://files.realpython.com/media/assert.f6d344f0c0b4.png)

__Have a look at the following example, where it is asserted that the code will be executed on a Linux system:__

    import sys
    assert ('linux' in sys.platform), "This code runs on Linux only."

If you run this code on a Linux machine, the assertion passes. If you were to run this code on a Windows machine, the outcome of the assertion would be False and the result would be the following:

    Traceback (most recent call last):
    File "<input>", line 2, in <module>
    AssertionError: This code runs on Linux only.