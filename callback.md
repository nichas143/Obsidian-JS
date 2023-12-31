> [!note] Call back Functions 
> A function passed as a parameter in a higher order function is called the callback function. 

```js
document.addEventListener('click',function doThis(){
  ...
})
```
in the example, addEventListener  is a higher order function, and passed function doThis() which will be called once the click even happens is called a [[callback]] function. 