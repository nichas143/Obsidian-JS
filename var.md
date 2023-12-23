- var follows [[hoisting]] in the block where its defined. 
- declared variables are function scoped, even if they appear inside a block by hoisting. 
	- Also note that *hoisting of only var variable happens not its value* if its not defined at the top. So the  reference error will not be raised. 

Note: 
see the following example exhibiting var's hoisting and function scope existence. 
```js
let three = 4;
function functionThree() {
	console.log(three); // undefined as only var three is hoisted not value
	{
		var three = 3;
	}
	console.log(three);  // 3 due to hoisting of var at function level and also the value declared it gives 3
}
functionThree();
```

```js
let three = 4;
function functionThree() {
	console.log(three); // 4
	{
		let three = 3; // let does not hoist.
	}
	console.log(three);  // 4
}
functionThree();
```

