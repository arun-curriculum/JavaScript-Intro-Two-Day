#JavaScript Continued

##JavaScript Objects

####Object Notation

```
var myObject = {
	firstName: "Arun",
	lastName: "Sood",
	role: "Instructor"
};
```

####Accessing Objects

```
myObject.firstName

myObject.lastName

myObject.role
```

####Objects can have multiple data types

```
var myObject = {
	firstName: "Arun",
	lastName: "Sood",
	sayName: function() {
		alert(this.firstName + " " + this.lastName);
	},
	age: 27
};
```

####`this` keyword

- `this` refers to the current object scope.
- In the case of `myObject` above, the current scope is `myObject`.
- I could have simply referred to it by `myObject`, but `this` is very DRY.
- You will see this syntax very often in "MVC"-type JavaScript frameworks such as Backbone.js.

##Object Exercises

Do the object exercises from [this repo](https://github.com/litterbox-sf-fall/notes/blob/master/week_01_fundamentals/day_3_intro_to_javascript/dusk_control_flow_and_functions/primitives_lab.md).

##Object Initialization

- `var myObject = {};` is basically the equivalent of var `myObject = new Object();`
- What happened here? We created a new instance of an object.

####Functions are objects too...

```
function Car(make, model, year) {
	this.make = make;
	this.model = model;
	this.year = year;
}

var myCar = new Car("Honda", "Civic", 2004);

console.log(myCar.make);
console.log(myCar.model);
console.log(myCar.year);
```

- What we've done is basically create a generic way to spit out objects containing the make, model, and year properties of any given car.
- This is very similar to the MODEL part of the MVC pattern of coding you will see later in the course.

##Object Enumeration

Iterating through objects can be achieved easily through a for-in loop. This will allow us to look through each key-value pair.

```
var myObject = {
	firstName: "Arun",
	lastName: "Sood",
	sayName: function() {
		alert(this.firstName + " " + this.lastName);
	},
	age: 27
};

for (var key in myObject) {
	console.log(key);
	console.log(myObject[key]);
}
```

##Object Exercise

####The Recipe Card

- Create an object to hold information on your favorite recipe. It should have properties for title (a string), servings (a number), and ingredients (an array of strings).
- On separate lines (one console.log statement for each), log the recipe information so it looks like:
	- Mole
	- Serves: 2
	- Ingredients:
	- Cinnamon
	- Cumin
	- Cocoa

##AJAX
- AJAX is a powerful way to create server requests and get responses without having to reload the page.
- AJAX stands for Asynchronous JavaScript and XML.
- Here is how it can be accomplished:

```
function reqListener () {
	console.log(this.responseText);
}

var oReq = new XMLHttpRequest();
oReq.onload = reqListener;
oReq.open("get", "[Endpoint Here]", true);
oReq.send();
```

- XMLHttpRequest is an object that contains the methods to send AJAX requests.
- The most important method here is `.open`, which takes three parameters:
	- Type of request
	- URL endpoint
	- Asynchronous true or false
- `.send` submits the request.

##AJAX Exercise
- Let's make a request out to `http://daretodiscover.herokuapp.com/users`.
- We can evaluate how we can get data into the console about each user.

##In-Class Lab / Homework
- Make a GET request call out to `http://daretodiscover.herokuapp.com/wines`.
- Take the returned data and create a simple HTML template to show the data for each wine.