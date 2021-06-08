# class-02

__* What does .map() return ?

__** return to the Components like : **__

* variable 
* elements 
* numbers 
* values

__* If I want to loop through an array and display each value in JSX, how do I do that in React ?*__

we can do that by map function

__* Each list item needs a unique *__. 

### ID

__* What is the purpose of a key ?*__

**Keys help React identify which items have changed, are added, or are removed** 

# The Spread Operator 

__* What is the spread operator ?*__

**The spread operator is a useful and quick syntax for adding items to arrays, combining arrays or objects, and spreading an array out into a function’s arguments.**

__* List 4 things that the spread operator can do.*__

* Adding to state in React

* Adding an item to a list

* Using an array as arguments

* Converting NodeList to an array

__* Give an example of using the spread operator to combine two arrays. *__


    const myArray = [`🤪`,`🐻`,`🎌`]
    const yourArray = [`🙂`,`🤗`,`🤩`]
    const ourArray = [...myArray,...yourArray]
    console.log(...ourArray) // 🤪 🐻 🎌 🙂 🤗 🤩



__* Give an example of using the spread operator to add a new item to an array. *__

    const fruits = ['🍏','🍊','🍌','🍉','🍍']
    const moreFruits = [...fruits];
    console.log(moreFruits) // Array(5) [ "🍏", "🍊", "🍌", "🍉", "🍍" ]
    fruits[0] = '🍑'
    console.log(...[...fruits,'...',...moreFruits]) //  🍑 🍊 🍌 🍉 🍍 ... 🍏 🍊 🍌 🍉 🍍

__* Give an example of using the spread operator to combine two objects into one.*__


    [...["😋😛😜🤪😝"]] // Array [ "😋😛😜🤪😝" ]
    [..."🙂🙃😉😊😇🥰😍🤩!"] // Array(9) [ "🙂", "🙃", "😉", "😊", "😇", "🥰", "😍", "🤩", "!" ]

    const hello = {hello: "😋😛😜🤪😝"}
    const world = {world: "🙂🙃😉😊😇🥰😍🤩!"}

    const helloWorld = {...hello,...world}
    console.log(helloWorld) // Object { hello: "😋😛😜🤪😝", world: "🙂🙃😉😊😇🥰😍🤩!" }

__* In the video, what is the first step that the developer does to pass functions between components? *__
creating a function 


__* In your own words, what does the increment function do? *__

increment as a function a way toe ling the father and the chilled and and increasing the count in the function   