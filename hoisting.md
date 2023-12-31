The first is commonly called hoisting: when all variables
declared anywhere in a scope are treated as if they’re declared
at the beginning of the scope

- functions are hoisted at the top of the function scope where they are declared (containing function) or global scope. 

###  function declaration -> hoisting 
```js
one();

function one() {
	console.log("hi how are u");
}
```
Above function hoisting get the code to run and get the outcome. 

### function expression has **no** hoisting
```js
one(); // TypeError: two is not a function

var two = function one() {
	console.log("hi how are u");
}
```
- the variable `one` is declared but not referenced to function `one()`
- here `one` is variable, and is hoisted and initialised to `undefined`  and available to be used. 
- So var one is hoisted and initialised to `undefined` even the function `one()` is hoisted. 

#### See the example which explains hoisting in var & function
```js
studentname = "sachin";
one();
function one() {
	console.log(`studentname = ${studentname}`);
}
var studentname;
```

> ### Hoisting metaphor
> Functions are hoisted first and then immediately after that var variable is hoisted.

So the above program is re-arranged as 
```js
function one() {
	console.log(`studentname = ${studentname}`);
}
var studentname;
studentname = "sachin";
one();
```

So hoisting is a [[compile phase]] rearrangement of the code. 

### [[var]] variable declared two times. 

![[Screenshot 2023-12-23 at 2.45.50 PM.png|500]]

here the variable is declared and assigned twice hence there is no problem as the variable will be hoisted without any problem. 
- This cannot be done with [[let]]. 

#### Redeclaration of variables is an error with let 
```js
let variableName = 2;
let variableName = 3;// error
```

or 
```js
let variableName = 2;
var variableName = 3;// error
```

or 
```js
var variableName = 2;
let variableName = 3;// error
```

- The above syntax errors are to encourage bug prevention and good code writing practices. 


## Let and const also hoist. 
See this code 
![[Screenshot 2023-12-24 at 12.44.32 AM.png|300]]
- in above code - when [[var]] hoists, it hoists to the function or global level, but is intialised to `undefined` 

#### In let/const 
- But [[let]] and [[const]] do also hoists to the top of the block where its defined but is just declared but not initialised (neither to `undefined`) which can be seen in the below code. 
![[Screenshot 2023-12-24 at 12.46.56 AM.png]]
hence it seem the correct definition of hoisting is only declaring the variable at the top but initiation is not part of hoisting - authors remark. 

>[!note] Best practices #bestpractices 
>Declare [[let]] and [[const]] at the top of the block. 