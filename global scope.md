	  Global scope is where all the stitching of the files take place in JS. 
Understanding the global scope is critical in understanding the complete [[lexical scoping]]


Global scope is also where 
-  JS exposes its built-ins:
	- primitives: undefined, null, Infinity, NaN – natives: Date(), Object(), String(), etc.
	-  global functions: eval(), parseInt(), etc. – namespaces: Math, Atomics, JSON
	- friends of JS: Intl, WebAssembly
- The environment hosting the JS engine exposes its own built-ins:
	- console (and its methods)
	- the DOM (window, document, etc)
	- timers (setTimeout(..), etc)
	- web platform APIs: navigator, history, geolocation, WebRTC, etc.

##### Note very few variables should be in the global scope (programmer created) to prevent future errors. 
Note  : Window is not always the global in all environments. 

---
### Shadowing global object properties with global variables 
Within Global scopes, global variable can shadow a global property with the same as - as in the below code. 
```js
window.something = 42;
let something = "kyle"; // global something variable is shadowing the global property of window object.

console.log(something); // kyle 
console.log(window.something); // 42
```

BUT IF 
```js
window.something = 42;
var something = "kyle"; // global something variable is shadowing the global property of window object.

console.log(something); // kyle 
console.log(window.something); // kyle
// here var overwrite the global property with global variable, and no shadowing effect is created.
```

So [[var]] at global prevents shadowing while [[let]] at global creates a shadowing with the global property like `window.variable` 

### Another odd behavior 
name is a window property of type string 
```js
var name = 42;
console.log(name, typeof name); // 42, string 
```

and if 
```js
let name = 42;
console.log(name, typeof name); // 42 number 
```
- note : [[let]] is able to shadow the name variable but not [[var]]
