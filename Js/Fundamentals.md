
#### Lexical environment
	stores variable and function within current scope and along with reference to all outer scope.
```
function outer() {  
  var x = 10;  
  function inner() {  
    // The lexical environment of `inner()` contains the variable `x` from `outer()`.  
    console.log(x);  
  }  
  inner();  
}  
outer();
```
The interpreter continues searching the lexical environment until it finds the variable or it reaches the global scope. If the variable is not found anywhere in the lexical environment, the interpreter throws a `ReferenceError` exception


#### Closure
	feature where an **inner function** has access to:
	1. **Its own scope** (variables defined inside it),
	2. **The scope of its outer function**, and
	3. **The global scope**.


```
function outerFunction() {
  let count = 0;

  function innerFunction() {
    count++;
    console.log(count);
  }

  return innerFunction;
}

const counter = outerFunction();
counter(); // 1
counter(); // 2
counter(); // 3
```

	
Benefits
	- Data encapsulation: functions that can't be accessed from outside the closure
	- Functional programming : retaining access to the scope  were created /ex curry
	- Event handlers and callbacks: maintain state or access variables
	- Module patterns: with private and public parts.
- Example: Create a counter, 
#### Compiler
JS and Node uses **just in time ** (JIT) compiler inside v8 engine. executes source code into machine code during run time rather than before execution 
- native add on like node and c++ modules are compiled with node-gyp, which uses GCC (C compiler ) or Clang
- Transpiler is different converts source -> bytecode -.> machine code (compatibility of es6 to es5, used in babel)