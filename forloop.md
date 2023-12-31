there are three for loops 
```js 
for (let i =0 ; i< something ; i++){

}
```
OR 
```js
for (line in list ){

}
```
Or 
```js
for (line of list){

}
```


### for (let i =0 ; ...)
```js 
for (let i = 0; i< n ;i++ ){
	
}
```
is to be seen as 
```js
let $$i=0;
for (/* nothing */; $$i < 3 ; $$i++){
	let i = $$i; 
	let value = i * 10; 
	console.log(`${i} : ${value}`); 
}
```