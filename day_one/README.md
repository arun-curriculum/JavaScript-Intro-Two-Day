#Introduction to JavaScript
- JavaScript is a versatile language that can be run on the front-end or back-end.
- JavaScript is a non-blocking language, implementing a call-stack and process-queue structure.
- Let's look at some of the building blocks of the language.

##Functions
- Functions allow you to write code that will be executed at a later time.
- They encapsulate logic regarding certain operations.
- Functions help you to not repeat yourself as often and reuse code.

##Defining a Function

- There are three general ways to define a function.
- Function naming:

```
function functionName() { }
```

- Function as a variable:

```
var functionName = function() { }
```

- Function in an object:

```
var object = {
	myFunction: function() { }
}
```

##Calling a Function

- In order to invoke a function, we need to "call" it.
- This is how we do it for each type:

```
functionName();

object.myFunction();
```

##Function Arguments

- Arguments allow you to pass data into functions.
- You can think of them as "temporary" variables that can only be used in that function.
- Arguments are passed in at the time of calling the function.

#####The Setup:

```
function addTwo(number1, number2) {
	return number1 + number2;
}
```

#####The Call:

```
addTwo(1, 2);
```

##Function Scope

- Data within functions stay within functions.

```
function defineVar() {
	var phrase = "Hello World!";
}

defineVar();

console.log(phrase);
```

- The variable "phrase" cannot be passed outside of the function.

##Return

- In order to get data outside of a function, it must be returned.
- This doesn't mean that your variables are now accessible; rather, resulting values are passed outside. Consider:

```
function addTwo(number1, number2) {
	number1 + number2;
}
```

- No data would result from this function unless it is "returned" out.
- How would we rewrite this?

##Self-Calling Functions

- Sometimes you want to have a function execute as soon as it is stored into memory.
- Self-calling functions are similar to `$(document).ready()` in jQuery.

```
(function() {
	//Your code here
})();
```

##JS Function Lab 1

Forget how old you are? Calculate it.
- Write a function called calculateAge that:
	- Takes 2 arguments: birth year, current year
	- Calculates the 2 possible ages based on those years
	- Outputs the result to the screen like so: "You are either NN or NN"
- Call the function three times with different sets of values.
- Bonus: Figure out how to get the current year in JavaScript instead of passing it in.

##Control Flow in JavaScript
- Often times you want to make sure certain blocks of code get activated under specific circumstances.
- Control flow structures help you specify when you want blocks of code to run based on a number of true/false conditions.

##Conditionals

- Standard `if, else` blocks
- Slightly more advanced `if, else if, else` blocks

##Comparison Operators

- AND `&&`, OR `||`
- `>`, `<`, `>=`, `<=`

## Exercise #1: The Marathon Runner

- Create a prompt that asks the user what their best marathon time was.
- If their time was between 4 to 5 hours, alert the user that their time was average.
- if the time was between 2 to 4 hours, alert the user that their time was excellent.
- If the time was greater than 4 hours, alert the user that they need to speed up!

## For loop

  ```
  var mixed = [1, "two", "three", true];
  
  console.log("For Loop:")
  
  // Most common mistake is using commas instead of "semicolons" inside the loop declaration.
  
  for(var i = 0; i < mixed.length; i++) {
    console.log("The element at index " + i + " is: " + mixed[i]); 
  }
  ```
  
## While loop

```  
var a = [1,2,3,4];
var b = [1,2,3,4];

console.log("While Loop:");
  
var i = 0;
  
while(i < a.length) {
	console.log("The element at index " + i + " is: " + a[i]);
	i++; 
}
```
  
##Infinite Loops

- While writing a loop it is possible to create a loop that will go until infinity.
- Obviously we try to avoid this while coding.

```
for (var i = 0; i > 0; i++) {
	console.log(i);
}
```

##Control Flow Exercise: 
- Write a for loop that will iterate from 0 to 20. 
- For each iteration, it will check if the current number is even or odd, and report that to the screen (e.g. "2 is even").
- Do this using a `FOR` and a `WHILE` loop.

##JavaScript Arrays
- An array is a data type that allows you to store multiple pieces of information in one place.
- The data inside of an array can be in multiple data formats - array, object, function, string, etc.
- Arrays use the standard bracket notation: `[]` and operate using indexes.
- Let's try some examples in the console.

##Array Functions

###.push()

The `.push` method allows you to add new items to the end of an array and returns the new length.

```
var myArray = ["Apple", "Banana", "Orange"];

myArray.push("Grape", "Peach");
```

###.pop()

The `.pop` method removes the last element of an array and returns that element. This will actually change the array.

```
var myArray = ["Apple", "Banana", "Orange", "Grape"];

myArray.pop();

//Array is now ["Apple", "Banana", "Orange"];
```

###.shift()

The `.shift` method removes the first element of an array and returns that element. This will also change the array.

```
var myArray = ["Apple", "Banana", "Orange", "Grape"];

myArray.shift();

//Array is now ["Banana", "Orange", "Grape"];
```

###.unshift()

The `.unshift` method adds one or more elements to the beginning of an array and returns the length of the new array. This will change the array.

```
var myArray = ["Apple", "Banana", "Orange", "Grape"];

myArray.unshift("Peach");

//Array is now ["Peach", "Banana", "Orange", "Grape"];
```

###.forEach()

The `.forEach` method executes a provided function once per array element.

Let's say we want to display the result of adding 2 to each index of the below array:

```
var myArray = [1, 2, 3, 4];

myArray.forEach(function(element, index, array) {
	console.log(element + 2);
});
```

###.map()

Array mapping allows you to create a new array from running some provided function on each index of the given array.

Let's say we want to multiply every number in the below array by 2 to produce a new array:

```
var myArray = [2, 3, 4, 5];

var newArray = myArray.map(function(currentValue, index, array) {
	return currentValue * 2;
});
```

###.reduce()

Array reduce allows you to run a function on all array indexes and return a single value. Let's say we wanted to add together all of the items in this array:

```
var myArray = [2, 3, 4, 5];

var sum = myArray.reduce(function(previousValue, currentValue, index, array) {
	return previousValue + currentValue;
});
```

##Array Exercises

Do the array exercises from [this repo](https://github.com/litterbox-sf-fall/notes/blob/master/week_01_fundamentals/day_3_intro_to_javascript/dusk_control_flow_and_functions/primitives_lab.md).