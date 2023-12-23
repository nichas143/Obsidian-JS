All [[functions]] by default reference an empty object at property name [[prototype object]]. 

> Prototype object 
> is the prototype object to which other objects link to when the function is called by `new`

To set a prototype for objects we need to use 
`newObj = Object.create(oldObject)` - this create a link between newObj and oldObj prototypal link 
```js
let human = {
talk: true,
sing() {
	if (this.talk) {
		return "can sing";
	} else {
		return "cannot sing";
		}
	},
};
let monkey = Object.create(human);
monkey.talk = false;
console.log(human);
console.log(monkey);
console.log(monkey.sing());
console.log(human.sing());
```

see results below 
![[Screenshot 2023-12-22 at 5.05.43 PM.png]]

The above program also show how [[this]]  - using [[execution context]] points to the corresponding object. 