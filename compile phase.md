Compile/Parse phase happens before execution phase. 
- Compile phase takes care of 
	- lexical scoping 
	- defining source and target of the variables. 

There are three parts of lexical scoping 
- block scope 
- function scope
- global scope.

And the mental model while we check the scoping is done as under - 
variables declared in outer scopes are accessible in the inside scope (much mathematically opposite to how set theory subset works)

Mental model to understand scoping of variables is conversation between 
- Engine 
- Compiler 
- Scope manager - (global, function and local ) there are three.. 

#### Mental Model 
##### Compiler and Scope manager (Compilation phase)
On encountering a variable the control first goes to the scope manager (of that scope which ever of the three it is) if the reply is NO then the compiler asks the outer scope manager about the variable. So if a variable is encountered at block level, and not declared at that level then the the function scope manager is asked and then if not there then global scope manager is asked. 

##### Engine and Scope manager (Execution phase)
Similar conversation happens and here the target and source are identified and assignments are done. So in a particular scope the variable is found the scope manager than the next outer scope is checked. 

> Best practice is to use `use strict` so that bad issues are taken care of. Since at times if the variable is not declared in the current scope, then the outer scopes are accessed and if that is not found then at the end the global scope manager creates the variable since `strict` mode is not enabled. 