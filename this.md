`this` is a run-time [[binding]]. 
- this binding has nothing to do with where a function is declared, but has instead everything to do with the manner in which the function is called. 

### What all happens
when a function is invoked 
- an activation record (called as [[execution context]]) is created. 
- this record contains information about from where the function was called from ([[call stack]]), how the function was invoked, what parameters were passed. 
- One of the properties of the record is the `this`  reference, which can be used for the duration of the function. 

> this is actually a binding that is made when a function is invoked, and what it references is determined entirely by the call-site where the function is called. 

### Call-site 
- *this binding* can be understood through the call-site. 
- *call-site* - the location in code where a function is called (not where its declared)
to know the call-site - we need to see the [[call stack]] 
- the call-site we care about is in the invocation before the currently executing function. 

Lets see the example, 
```js
function baz() {
console.log(this);
bar();
}
function bar() {
console.log(this);
foo();
}

function foo() {
console.log(this);
}
baz();
// first we write the call-stack (the order in which the functions are called ) and then correspondingly create the call-site writing the the environment from where the corresponding call (function call) was made.
```

See the order in which the functions are called (not the declarations )
`Call stack : baz --> bar --> foo`  (now we write the corresponding  order from where the call was made i.e. call site)
`Call-site : global -> baz -> foo.`

