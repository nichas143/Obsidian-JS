>[!note] Execution context
>One way to think about the execution context is that it’s
a tangible object whose properties are made available to a
function while it executes

```js


```

Execution context is exposed to a function via the `this`  keyword.

> Scope is static and contains a fixed set of variables available
at the moment and location you define a function, but a
function’s execution context is dynamic, entirely dependent on how its called (regardless of where it is defined or even called from)

> `this` is not a fixed characteristic of a function based on
the function’s definition, but rather a dynamic characteristic
that’s determined each time the function is called.

Not all [[Functions]] will have an execution context. 