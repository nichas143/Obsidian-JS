```js
function Classroom () { 
	// a function declaration
}

Classroom.prototype.welcome = function hello() { 
	console.log("welcome, students")
}

var mathClass = new Classroom();

mathClass.welcome() ; // Welcome students 
```

This is same as implemented in [[Class definition]] . Here `Classroom.prototype` is an object of class `Classroom.  

This above structure is currently in ES6 implemented as 

![[Class definition]]