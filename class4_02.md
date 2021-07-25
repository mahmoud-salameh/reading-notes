# In Tests We Trust — TDD with Python:

__**So, you wanna do some tests, right?**__
Some time ago, when I was beginning my career as a programmer, I heard other programmers talking about two things: refactoring and unit tests. To be honest, they just talk about refactoring to explain why this practice should be avoided (and how scared they were to do it) and about unit tests to say they are too expensive to begin with, that they spend a lot of time, etc. Unit tests did sound like a utopian dream.

__**The freela**__

**Imagine that a client has a website and through it he receives a lot of contacts from potential customers. After a while he realized that it is important for the business to identify the profile of consumer: age, gender, job and so on. But the website just receive the name and the email.**
**They hired you to identify the gender of a person based on his/her name. Luckily, there is an amazing API called [Genderize.io](https://www.anapaulagomes.me/en/2017/09/07/In-Tests-We-Trust/Genderize.io) that identifies the possible genders. And you quickly developed your API connection:**

However the client demands you to write unit tests and you are curious about TDD. Here our journey begins!

__**TDD is not about the money/tests**__

One of the things that amaze me about TDD is how we can grow our software design consciously and well, just building what is needed to make the test pass. When we are writing tests we are forced to think about the design first and how we can break it into small pieces.

Let’s write one more test. Besides female names, we need to identify male names as well.

**{def test_should_return_male_when_the_name_is_from_male_gender():
    detector = GenderDetector()
    expected_gender = detector.run(‘Pedro’)
    assert expected_gender == ‘male’}**

 __But when we run it will fail because we just return female, right? Let’s fix it using our real code.__
   ___import requests

 def run(self, name):
    result = requests.get('https://api.genderize.io/?name{}'
 .format(name))
    return result['gender']__

![Now our tests are passing! Yay!](https://miro.medium.com/max/875/1*gxEKnrQuS7CO3hONTD7_hg.png)

{What does the if __name __ == “__main __”: do?}

__Before executing code, Python interpreter reads source file and define few special variables/global variables.__

    **If the python interpreter is running that module (the source file) as the main program, it sets the special __name__ variable to have a value “__main__”. If this file is being imported from another module, __ name__will be set to the module’s name. Module’s name is available as value to __name__ global variable.**

__A module is a file containing Python definitions and statements. The file name is the module name with the suffix .py appended.__

# Python program to execute
# main directly
print ("Always executed")

    if __name__ == "__main__":
	print ("Executed when invoked directly")
else:
	print ("Executed when imported")

* All of the code that is at indentation level 0 [Block 1] gets executed. Functions and classes that are defined are, well, defined, but none of their code runs.
*     Here, as we executed script.py directly __name__ variable will be __main__. So, code in this if block[Block 2] will only run if that module is the entry point to your program. 
*     Thus, you can test whether your script is being run directly or being imported by something else by testing __name__ variable.
* If script is getting imported by some other module at that time __name__ will be module name.

### Why Do we need it?
# Python program to execute
# function directly
    def my_function():
	print ("I am inside function")

# We can test function by calling it.
my_function()

### Now if we want to use that module by importing we have to comment out our call. Rather than that approach best approach is to use following code: 

# Python program to use
# main for function call.
    if __name__ == "__main__":
	my_function()

import myscript

myscript.my_function()

### __**Advantages : **__

    1-Every Python module has it’s __name__ defined and if this is ‘__main__’, it implies that the module is being run standalone by the user and we can do corresponding appropriate actions.
    2-If you import this script as a module in another script, the __name__ is set to the name of the script/module.
    3-Python files can act as either reusable modules, or as standalone programs.
    4-if __name__ == “main”: is used to execute some code only if the file was run directly, and not imported.

**This article is contributed by Nirmi Shah. If you like GeeksforGeeks and would like to contribute, you can also write an article using contribute.geeksforgeeks.org or mail your article to     contribute@geeksforgeeks.org. See your article appearing on the GeeksforGeeks main page and help other Geeks.
Please write comments if you find anything incorrect, or you want to share more information about the topic discussed above.**

##  What is difference between tailed and non-tailed recursion? 

A recursive function is tail recursive when recursive call is the last thing executed by the function. Please refer [tail recursion article](https://www.geeksforgeeks.org/tail-recursion/) for details. 
// A C++ program to demonstrate working of
// recursion
#include <bits/stdc++.h>
using namespace std;

    void printFun(int test)
    {
	if (test < 1)
		return;
	else {
		cout << test << " ";
		printFun(test - 1); // statement 2
		cout << test << " ";
		return;
	}
}

    // Driver Code
     int main()
    {
	int test = 3;
	printFun(test);
}

### Output : 
{3 2 1 1 2 3}

__**When printFun(3) is called from main(), memory is allocated to printFun(3) and a local variable test is initialized to 3 and statement 1 to 4 are pushed on the stack as shown in below diagram. It first prints ‘3’. In statement 2, printFun(2) is called and memory is allocated to printFun(2) and a local variable test is initialized to 2 and statement 1 to 4 are pushed in the stack. Similarly, printFun(2) calls printFun(1) and printFun(1) calls printFun(0). printFun(0) goes to if statement and it return to printFun(1). Remaining statements of printFun(1) are executed and it returns to printFun(2) and so on. In the output, value from 3 to 1 are printed and then 1 to 3 are printed. The memory stack has been shown in below diagram.**__

![img](https://media.geeksforgeeks.org/wp-content/cdn-uploads/recursion.jpg)

     // C++ code to implement Fibonacci series
    #include <bits/stdc++.h>
    using namespace std;

    // Function for fibonacci

    int fib(int n)
    {
	// Stop condition
	if (n == 0)
		return 0;

	// Stop condition
	if (n == 1 || n == 2)
		return 1;

	// Recursion function
	else
		return (fib(n - 1) + fib(n - 2));
    }

    // Driver Code
    int main()
    {
	// Initialize variable n.
	int n = 5;
	cout<<"Fibonacci series of 5 numbers is: ";

	// for loop to print the fiboancci series.
	for (int i = 0; i < n; i++)
	{
		cout<<fib(i)<<" ";
	}
	return 0;
    }

### Output

 __**Fibonacci series of 5 numbers is: 0 1 1 2 3 **__ 