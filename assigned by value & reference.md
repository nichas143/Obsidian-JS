[[primitives]] are always assigned by value 

```js 
let a = 2; 
let b = a;
a = 3 ;
console.log(`a = ${a}, b=${b}`) // a= 3, b=2 
```

[[objects]] are assigned by reference 

```js
console.log([1,2,3] === [1,2,3]); // false 
let arrayOne = [1,2,3];
let arrayTwo = [1,2,3];
console.log(arrayOne === arrayTwo); 
let arrayThree = arrayOne ;
let arrayThree = [2,3,4]; 
console.log(arrayOne, arrayTwo, arrayThree)
```

