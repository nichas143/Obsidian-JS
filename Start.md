We will study JS 

JS consists of Values. Functions, primitives all are values. [[Values]] are of two kinds - 

## Pillar 1 : [[Scope]] and [[Closure]] 
Scopes are like buckets and variables are like marbles. 

> [[lexical scoping]] : problem able to access variables in a particular scope is called *lexical scoping*

JS does not seem to be lexical scoped because of two characteristics of it 
1. [[hoisting]]  & 
2. [[var]]-declared variables are function scoped, even if they appear inside a block.
3. let/const declarations have a peculiar error behavior called the “[[Temporal Dead Zone]]” (TDZ) which results in observable but unusable variables. Though TDZ can be strange to encounter, it’s also not an invalidation of lexical scoping.

[[Closure]] is a natural result of lexical scope when the language
has functions as first-class values, as JS does

## Pillar 2 : [[Prototypes]]
JS is one of very few languages where you have the option
to create objects directly and explicitly, without first defining
their structure in a [[class]].

prototype system: the ability for two objects to simply
connect with each other and cooperate dynamically (during
function/method execution) through sharing a this context

Classes are just one pattern you can build on top of such
power. But another approach, in a very different direction, is
to simply embrace objects as objects, forget classes altogether,
and let objects cooperate through the prototype chain. This is
called behavior delegation. I think delegation is more power-
ful than class inheritance, as a means for organizing behavior
and data in our programs.

## Pillar 3: [[Types]] and [[Coercion]]



---
[[compile phase]] is where we start our discussion in Book2. 
[[shadowing]] is another concept, is where the global variable and local variable has the same names. And inside the local scope the global scope can now way be executed or accessed (other than `Window.shadowedVariable`)  




