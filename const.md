const is used to define a variable and such variable cannot be assigned with new value again. 
Moreover const variable has be assigned when declared. 

```js
const variable = 'constant value'; 
const varNew; // will throw an error
```

- const should be used with only primitives #bestpractices 
- const used with objects won't allow the entire object reassigned but parts of the object can be reassigned. 

```js
const value = 10;
const arrName = [1,2,3];
arrName = [] ; // throws an error 
arrName[2] = 4; // is perfectly fine. // hence not to use. 
```