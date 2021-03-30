## **_choosing a text editor_**
I think it ends up being a very personal choice, as personal as the sports teams
you support.
When you use the text editor that you love, cherish and swear by to make a complete web site successfully and to your satisfaction.
 Then fantastic, clearly the text editor you’ve chosen got the job done.

The Difference Between **Text Editors** and **IDEs**
A text editor kind of gives away what it does in the title—it edits text. It also manages text, and manages files.   
I love that name ""text
wrangler"" because in a way that’s what really a text editor does. It wrangles your text together into something meaningful. An IDE (Integrated Development Environment) is really a suite of
different software all coming together. An IDE is a text editor, a file
manager, a compiler, and a debugger all in one software package.

The **terminal** may seem daunting but don't fret. **_Linux_** is full of shortcuts to help make your life easier. You'll be introduced to 
several of them throughout this tutorial. Take note of them as not only do they make your life easier, they often also save you from making silly mistakes such as typos.

a lot of commands in **_linux_** are named as an abbreviation of a word or words describing them. This makes it easier to remember them
like ls(list), pwd( Print Working Directory),cd(change Directories).

thing we need to appreciate with **_linux_** is that under the hood, everything is actually a file. A text file is a file, a directory is a file your keyboard is a file (one that the system reads from only), your monitor is a file (one that the system writes to only).

Spaces in file and directory names are perfectly valid but we need to be a little careful with them. As you would remember, a space on the command line is how we seperate items. They are how we know what is the program name and can identify each command line argument. If we wanted to move into a directory called Holiday Photos for example the following would not work.

ls Documents
FILE1.txt File1.txt file1.TXT Holiday Photos
...
cd Holiday Photos
bash: cd: Holiday: No such file or directory

The first approach involves using quotes around the entire item. You may use either single or double quotes (later on we will see that there is a subtle difference between the two but for now that difference is not a problem). Anything inside quotes is considered a single item.

cd 'Holiday Photos'
pwd
/home/ryan/Documents/Holiday Photos
