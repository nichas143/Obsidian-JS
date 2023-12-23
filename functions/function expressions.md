defined as 

#### Anonymous function expression (there is no name assigned)
```js
const funcName = function () { 
}
```
or 
#### named function expression (one being the name)
```js
const funcName = function one () {

}
```

are called expressions 

- in function expression the scope of the identifier of the function is in enclosing scope but not the function identifier. See the program. 
```js
var askQuestion = function ofTheTeacher() {
console.log(ofTheTeacher);
};
askQuestion();
console.log(askQuestion);
console.log(ofTheTeacher);
```

![[Screenshot 2023-12-23 at 9.30.26 AM.png|500]]
> see that the function name `ofTheTeacher` does not exist. 

