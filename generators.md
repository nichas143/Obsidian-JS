generators are special type of function, which produce multiple values, on a per request basis, while suspending the execution between these requests. 

> Generators are iterators. 


![[Screenshot 2023-12-30 at 10.25.47 PM.png|400]]
its easy to understand what happens with constructor functions 
- the function keyword has a `*`
- the keyword `yield`  returns `++id`  and then the function suspends. 
- on `.next()`  the execution starts post the previous `yield` and continues till the next value is yielded. 

> [!NOTE]
> - calling a generator function creates an object called as `iterator`
> - through this iterator object we can communicate with the generator. 
> - using the `next()` method we can control the generator by requesting a value. 
> - `iterator.next()`  executes the code of the constructor till the next `yield` keyword is reached and returns an object that encapsulates the results and tells us if the work is done or not. 
> - `iterator.next().done` stores the done status of the work. 

#### Example code - iterator.next().done
![[Screenshot 2023-12-30 at 11.27.05 PM.png|400]]
- this code explains, that `idIterator.next().done` gives if the constructor has come to its end or not. 

## delegating to another generator 
![[Screenshot 2023-12-30 at 11.43.20 PM.png|500]]

See how the call to another generator in a generator is done with `yield*`  keyword. 

## Sending values to generators 

