Instead of arranging for a a function ([[callback]]) to be called at some point in the future, return an object that represents this future event ([[promise]])

This object that represents  a future event is called a class Promise. 

> A promise is asynchronous action that may complete at some point and produce a value. It is able to inform anyone who is interested when is value is available. 

### Creation 
The easiest way to create a promise is calling `Promise.resolve` . 
`resolve` makes sure that the value you give is wrapped in a promise. 
- If it’s already a promise, it is simply returned (that means the same promise is returned) 
- otherwise, you get a new promise that immediately finishes with your value as its result.
see the example, 
```js
let fifteen = Promise.resolve(15);
fifteen.then((value)=> console.log(`Got value ${value}`));
```
here fifteen is again is a promise that will resolve to 15. 
then executes the function. 

### .then()
to get result of a promise you use the `.then()` method. 

A normal value is simply there. A promised value is a value that might already be there or might appear at some point in the future.

### Constructor
To create a promise, you can use `Promise` as a constructor. It has a somewhat odd interface—the constructor expects a function as argument, which it immediately calls, passing it a function that it can use to resolve the promise. It works this way, instead of, for example, with a resolve method, so that only the code that created the promise can resolve it.


> [!note] Index 
> - convert callbacks to promises
> - how to create promises 
> - how to use promises 
> - why? we should use promises. 
> - different phases of promises 
> - error handling 
> - chaining multiple promises 

