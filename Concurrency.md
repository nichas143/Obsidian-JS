We need two separate (at least) processes to be executing simultaneously but not necessarily at the same instant. 

>[!note] Concurrency 
> is when two or more processes are executing simultaneously  over the same period whether their individual constituents operations happen in parallel. 

### Non interacting Concurrency  
There are processes  that need not interact between each other. 

```js
var res = {} 
function foo(results) {
	res.foo = results; 
}
function bar(results){
	res.bar = results; 
}
ajax("apipath1",foo)
ajax("apipath2",bar)
```

- in the above program which  `ajax`  calls are executed first does not matter for the problem, since the variables foo and bar are not interacting with each other. 

### Interactive Concurrency
Commonly,  concurrent "processes" will by necessity interact , indirectly through scope and/or the DOM

```js
var res = [];
function response(data){
	res.push(data);
}
ajax("apipath1",response )
ajax("apipath2",response )
```

Now here we don't know if the `apipath1`  response is pushed into the `res` array or `apipath2` response is pushed, hence they are interacting with the scope shared by them with the variable `res`

This can be fixed by the following changes in the above code. #bestpractices 
```js
var res = [];
function response(data){
	if (data.url == "apipath1"){
		res[0] = data;
	} else if (data.url == "apipath2"){
		rest[1] = data;
	}
}
ajax("apipath1", response);
ajax("apipath2", response);
```

- above code makes sure `res`  first location contains first api response and second correspondingly. 

#### Always broken concurrency 
```js
var a, b; 

function foo(x) {
	a = x*2;
	baz();
}
function bar(y) {
	b = y*2;
	baz();
}
function baz(){
	console.log(a+b);
}
ajax(api1,foo);
ajax(api2,bar);
```
- this code is always broken. 

> how to fix it 
```js
var a,b;
function foo(x){
	a = x*2;
	if (a && b){
		baz();
	}
}
function bar(y){
	b = y*2;
	if (a&& b){
		baz();
	}
}
ajax(api1,foo);
ajax(api2,bar);
```

How to fix if there are many calls done and we only want the first call to be successful. 
```js
var a;
function foo(x){
	a = x*2;
	baz();
}
function bar(x){
	a=x/2;
	baz();
}
ajax(api1,foo);
ajax(api2,bar); // which ever is the first will overwrite the second. 

```
- // which ever is the first will overwrite the second. 

> to fix this we do the following its called 
> ### LATCH

```js
var a; 
function foo(x){
	if (!a){
		a = x*2;
		baz();
	}
}

function bar(x){
	if (!a){
		a = x/2;
		baz();
	}
}
ajax(api1,foo);
	ajax(api2,bar); // only the first call will be executed rest will be neglected5
```