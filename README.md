# Sprint Challenge - JavaScript Fundamentals

**Read these instructions carefully. Understand exactly what is expected _before_ starting this Sprint Challenge.**

This challenge allows you to practice the concepts and techniques learned over the past week and apply them in project. This Sprint explored JavaScript Fundamentals. During this Sprint, you studied array methods, this keyword, prototypes, and class syntax. In your challenge this week, you will demonstrate proficiency by completing a range of JavaScript problems.

This is an individual assessment. All work must be your own. Your challenge score is a measure of your ability to work independently using the material covered through this sprint. You need to demonstrate proficiency in the concepts and objectives introduced and practiced in preceding days.

You are not allowed to collaborate during the sprint challenge. 

## Introduction

The index.js file contains all of your challenges. Please review it in full before answering the questions. If you complete the stretch goals please leave them in your file but commented out so that they do not affect the MVP tasks. 

In meeting the minimum viable product (MVP) specifications listed below, you should have all tests passing. You can console.log to check your work and ensure you are submitting the correct results. 

### Commits

Set up codegrade early and commit your code regularly and meaningfully. 

## Interview Questions
### (please edit this file and write your answer below each question.)
Demonstrate your understanding of this week's concepts by answering the following free-form questions.

Edit this document to include your answers after each question. Make sure to leave a blank line above and below your answer so it is clear and easy to read.

1. Explain the differences between `.map`, `.reduce` and `.filter` and describe a use case for each. 

**.map()**
.map() called on a given array calls a function for each item in the array; it returns a new array that's populated with the results.

    *Example* 
    const exampleArray = [2, 4, 6, 8]
    <!-- Setting up an example array full of items to be copied -->
    const solutionArray = exampleArray.map(x => x * 24)
    <!-- Saved a copy of a called array with .map(), which will execute a function on each item in the exampleArray and populated the new array, solutionArray, with the results of that function. -->
    console.log(solutionArray);
    <!-- expected result: 48, 84, 144, 192 -->


**.reduce()**
.reduce() executes a callback function on each element in an array, "passing in the return value from the calculation on the preceding element." (sic MDN)
MDN also says that the easiest way to understand .reduce() is to return the sum of all elements in an array. So, I'll do that now!

    *Example*
    const anArray = [3, 6, 9]
    <!-- An array to start with. -->
    const initialValue = 0;
    <!-- We need to initialize with a beginning value. If this is declared, `currentValues` is initialized as the first value in the array... If it ISN'T declared, `previousValues` becomes the first item in the array, and ``currentValue` becomes the second.-->
    const sum = anArray.reduce(
        (previousValue, currentValue) => previousValue + currentValue,
        <!-- Pretty sure you can use whatever variable names you want here, just make sure it's semantic enough to be understand in the context of the code. .reduce() is pretty confusing especially for beginner JS learners, so the pros and cons need to be carefully weighed against reduce() and other methods... -->
        initialValue
        <!-- this was saved as a variable, but if you don't declare it as a variable you can use an actual number here. -->
    );
    console.log(sum);
    <!-- This will print 18 -->

**.filter()**
The .filter() method will create a new array filled with all items in a given array that pass a user specified test.


    *Example*
    const box = [
        <!-- Gotta make an array! -->
        {object: `mushroom lamp`, type: `clutter`},
        {object: `novelty can opener`, type: `clutter`},
        {object: `old cat collar`, type: `memory`},
        {object: `thumb drive`, type: `data`},
        {object: `gum wrapper`, type: `trash`}
    ]

    const trash = box.filter(stuff => stuff.type = `trash`);
    <!-- Arrow function to sift through the stuff -->
    console.log(trash);
    <!-- expected output: 
    [ { object: 'gum wrapper', type: 'trash' } ] -->


2. Explain the difference between a callback and a higher order function.

A higher order function is a function that accepts a callback function as an argument. A callback function is a function that is used later in a higher order function.

3. Explain what a closure is.

Closure allows you to protect all of your code from variables and nested functions that you only want to access within the scope of a specific function.

4. Describe the four principles of the 'this' keyword.

Globally, 'this' is the window, or console object.

    <!-- console.log(this) in the global scope, as in right here, right now, with no other indicators, will reference the whole window. In VSCode, it's represented as an empty object. `{}` -->

When a function is called using dot notation, the object before the dot is 'this'. 

    ernie.Call();
    <!-- ernie is 'this' -->

When creating a new object with a constructor function, 'this' is the object referred to inside of and returned by that function. 

    class HousePlant{
        constructor(props){
            this.name = props.name;
            this.type = props.type;
            this.soil = `fair`
        }
        checkSoil(){
            if (this.soil == `wet` && this.type == `succulent`){
                console.log(`${this.name} is probably a bit too wet. Consider leaving them by an open window.`)
            } else if (this.soil == `fair` || this.soil == `wet` && this.type !== `succulent`){
                console.log(`${this.name} is doing great. Good job!`})
            } else if (this.soil == `dry` && this.type == `succulent`){
                console.log(`Just a happy succ doin' its happy thing.`)
            } else if (this.soil == `dry` && this.type !== `succulent`){
                console.log(`Woah! It's time to water ${this.name}!!`)
            } else {console.log(`You've encountered an error. Write a dev!`)}
        }
        waterPlant(){
            if (this.soil == `dry`){
                this.soil = `fair`
            } else if (this.soil == `fair`){
                this.soil = `wet`
            } else {console.log(`Are you sure you want to water this plant? It's really wet.`)}
        }
    }
<!-- I call this so many times here, I hope it's apparent that I understand how to use it implicitly with dot binding and with new binding. -->
    const stanley = new HousePlant({name: `Stanley`, type: `echeveria`})
    stanley.checkSoil();

Finally there's explicit binding. You can call another object's functions with call or apply. We aren't likely to ever really need apply, so I'll use call in my example.

    const margaret = new HousePlant({name: `Margaret`, type: `hens and chicks`});

    stanley.waterPlant.call(margaret);

<!-- This waters Margaret, not Stanley. -->

5. Why do we need super() in an extended class?

        super() gives us inheritance. It passes on keys from parent functions and values, too, sometimes.

You are expected to be able to answer questions in these areas. Your responses contribute to your Sprint Challenge grade. 

## Instructions

### Task 1: Set up Project

Using VSCode and Command Line:


1. Fork the repo
2. Go into canvas and connect your repo to codegrade
3. Clone your forked version of the repo
4. DO NOT CREATE A BRANCH. You will be pushing your changes to the main/master today
5. cd into your repo
6. open the terminal in your vs code and type `npm install`
7. next type `npm run test` in your terminal
8. Complete your work making regular commits to main/master; your codegrade score will update each time you make a push.


### Testing & Debugging

Open a second terminal inside of your project by clicking on the split terminal icon
![alt text](assets/split_terminal.png "Split Terminal")

Inside of your second terminal type `npm start` 
![alt text](assets/npm_start.png "type npm start")

You will be running your tests in one terminal and debugging in the other. As you work on your code you should make use of `console.log` to check your progress and debug.
![alt text](assets/tests_debug_terminal_final.png "your terminal should look like this")

### Task 2: Project Requirements (MVP)

You must complete all tasks inside of `index.js` and answer the questions above.

In your solutions, it is essential that you follow best practices and produce clean and professional results. Schedule time to review, refine, and assess your work and perform basic professional polishing including spell-checking and grammar-checking on your work. It is better to submit a challenge that meets MVP than one that attempts too much and does not.

## Resources
 
 [Sprint Challenge Study Guide](https://www.notion.so/bloomtech/Unit-1-Sprint-3-Study-Guide-033a9a00659a4ef98c12eb97e49a6110)

## Submission format

Please submit your project via codegrade by following [these instructions](https://bloomtech.notion.site/bloomtech/BloomTech-Git-Flow-Step-by-step-269f68ae3bf64eb689a8328715a179f9) (see part 2, submitting an assignment with codegrade).
