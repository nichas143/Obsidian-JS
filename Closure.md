Closure is when a function remembers and continues to access variables from outside its scope, even
when the function is executed in a different scope.

### Characteristics of closure 
- Closure is part of the nature of a function
- Objects don't get closures, functions do get it. 

> to observe a closure you must execute a function in a different scope than where that function is originally defined. 

```js
function greeting(msg) {
	return function who(name) {
	console.log(`${ msg }, ${ name }!`);
	};
}
var hello = greeting("Hello");
var howdy = greeting("Howdy");
hello("Kyle");
// Hello, Kyle!
hello("Sarah");
// Hello, Sarah!
howdy("Grant");
// Howdy, Grant!
```

When the greeting(..) function finishes running, normally
we would expect all of its variables to be garbage collected
(removed from memory). We’d expect each msg to go away,
but they don’t. The reason is closure. 

> Closure is most common when working with asynchronous
code, such as with callbacks

```js
for (let [idx,btn] of buttons.entries()) {
	btn.addEventListener("click",function onClick(){
	console.log(`Clicked on button (${ idx })!`);
	});
}
```

> [!important] important
A closure is the closed-over variable environment of the execution context in which a function was created, even after that execution context is gone;

- Along with the scope of their access of variables (which is a static concept ) -  **closure**; they also have a characteristic of which is dynamic - **[[execution context]]** 

