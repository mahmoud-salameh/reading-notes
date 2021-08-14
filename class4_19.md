# Python Regular Expression Tutorial

Regular Expressions, often shortened as regex, are a sequence of characters used to check whether a pattern exists in a given text (string) or not. If you've ever used search engines, search and replace tools of word processors and text editors - you've already seen regular expressions in use. They are used at the server side to validate the format of email addresses or passwords during registration, used for parsing text data files to find, replace, or delete certain string, etc. They help in manipulating textual data, which is often a prerequisite for data science projects involving text mining.

This tutorial will walk you through the important concepts of regular expressions with Python. You will start with importing re - Python library that supports regular expressions. Then you will see how basic/ordinary characters are used for performing matches, followed by wild or special characters. Next, you'll learn about using repetitions in your regular expressions. You'll also learn how to create groups and named groups within your search for ease of access to matches. Next, you'll get familiar with the concept of greedy vs. non-greedy matching.

This tutorial also covers some very useful functions provided by the re library, such as: compile(), search(), findall(), sub() for search and replace, split(), and some more. You will also learn about compilation flags that you can use to make your regex better.

### Regular Expressions in Python

In Python, regular expressions are supported by the re module. That means that if you want to start using them in your Python scripts, you have to import this module with the help of import:

    import re

The re library in Python provides several functions that make it a skill worth mastering. You will see some of them closely in this tutorial.

### Basic Patterns: Ordinary Characters

You can easily tackle many basic patterns in Python using ordinary characters. Ordinary characters are the simplest regular expressions. They match themselves exactly and do not have a special meaning in their regular expression syntax.

__Examples are 'A', 'a', 'X', '5'.__

    pattern = r"Cookie"
    sequence = "Cookie"
    if re.match(pattern, sequence):
        print("Match!")
    else: print("Not a match!")

    Match

The match() function returns a match object if the text matches the pattern. Otherwise, it returns None. The re module also contains several other functions, and you will learn some of them later on in the tutorial.

Do you notice the r at the start of the pattern Cookie?
This is called a raw string literal. It changes how the string literal is interpreted. Such literals are stored as they appear.

### Wild Card Characters: Special Characters

Special characters are characters that do not match themselves as seen but have a special meaning when used in a regular expression. For simple understanding, they can be thought of as reserved metacharacters that denote something else and not what they look like.

Back to the special characters now.

     . - A period. Matches any single character except the newline character.

        re.search(r'Co.k.e', 'Cookie').group()
        'Cookie'


This is helpful if you want to make sure a document/sentence starts with certain characters.

    re.search(r'^Eat', "Eat cake!").group()

    ## However, the code below will not give the same result. Try it for yourself:
    # re.search(r'^eat', "Let's eat cake!").group()
    'Eat'


This is helpful if you want to make sure a document/sentence ends with certain characters.

    re.search(r'cake$', "Cake! Let's eat cake").group()

    ## The next search will return the NONE value, try it:
    # re.search(r'cake$', "Let's get some cake on our way home!").group()
    'cake'

### Repetitions

It becomes quite tedious if you are looking to find long patterns in a sequence. Fortunately, the re module handles repetitions using the following special characters:


    + - Checks if the preceding character appears one or more times starting from that position.

    re.search(r'Co+kie', 'Cooookie').group()
    'Cooookie'


     * - Checks if the preceding character appears zero or more times starting from that position.
     # Checks for any occurrence of a or o or both in the given sequence
    re.search(r'Ca*o*kie', 'Cookie').group()
    'Cookie'

    ? - Checks if the preceding character appears exactly zero or one time starting from that position.
    # Checks for exactly zero or one occurrence of a or o or both in the given sequence
    re.search(r'Colou?r', 'Color').group()
    'Color'


### Grouping in Regular Expressions

The group feature of regular expression allows you to pick up parts of the matching text. Parts of a regular expression pattern bounded by parenthesis () are called groups. The parenthesis does not change what the expression matches, but rather forms groups within the matched sequence. You have been using the group() function all along in this tutorial's examples. The plain match.group() without any argument is still the whole matched text as usual.



    statement = 'Please contact us at: support@datacamp.com'
    match = re.search(r'([\w\.-]+)@([\w\.-]+)', statement)
    if statement:
    print("Email address:", match.group()) # The whole matched text
    print("Username:", match.group(1)) # The username (group 1)
    print("Host:", match.group(2)) # The host (group 2)

    Email address: support@datacamp.com
    Username: support
    Host: datacamp.com


    Another way of doing the same is with the usage of <> brackets instead. This will let you create named groups. Named groups will make your code more readable. The syntax for creating named group is: (?P<name>...). Replace the name part with the name you want to give to your group. The ... represent the rest of the matching syntax. See this in action using the same example as before...


    statement = 'Please contact us at: support@datacamp.com'
    match = re.search(r'(?P<email>(?P<username>[\w\.-]+)@(?P<host>[\w\.-]+))', statement)
    if statement:
    print("Email address:", match.group('email'))
    print("Username:", match.group('username'))
    print("Host:", match.group('host'))

    Email address: support@datacamp.com
    Username: support
    Host: datacamp.com

