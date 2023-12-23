[[Shadowing]] is a concept where the global and local variable share the same variable name. And there is no way we can access the global variable. 
```js
let studentName1 = "Suzy";
function printStudent(studentName1) {
studentName1 = studentName1.toUpperCase();
console.log(studentName1);
}
printStudent("Sachin");
printStudent("gadkar");
console.log(studentName1);
```

![[Screenshot 2023-12-22 at 10.30.15 PM.png|600]]


Note only `var` declaration adds variable to the global window 
```js
var one = 1;
let notOne = 2;
const notTwo = 3;
class notThree {}
console.log(window.one);// 1 - only var variables are added to the Window env
console.log(window.notOne);//undefined
console.log(window.notTwo);//undefined
console.log(window.notThree);//undefined
```