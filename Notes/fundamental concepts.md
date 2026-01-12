 1. Dif between if else and ternary
		if/else - it is a statement, cant store a outcome
		ternary - it is expression, can store outcome

2.  console.log(1<2<3) // true
	1. 1<2 - true -> 1
	2. 1<3 -> true
    console.log(3>2>1) // false
	    3>2 -> true
		 1 > 1 -> false
	 JavaScript doesn't interpret these as mathematical expressions the way we might intuitively expect. Instead, it processes comparisons sequentially, converting boolean results to numbers when needed for the next comparison.	 
	 
3.  Arrow fn wiill take reference from parent scope
4. If you have an SQL query which is taking a lot of time . how will you debug . WHat all will you check
	   Execution Plan Analysis, Index Optimization, Query Structure Issues, Data Volume and Statistics, Resource Contention, Database Configuration, Query Rewriting, Data Model Issues
5. Array shuffle in O(n)
```
Math.floor(Math.random() * (i + 1));
```
6. Circular array
	```
	arr[(i%arr.length + n) % arr.length]
```
		````javascript
arr[(i % n + n) % n];
````
7. Removes= any whitespace character (space, tab, newline, etc.) (`/\s+/`)
```
// Regular split with single space "hello world test".split(" ") // Result: 
["hello", "", "world", "", "", "test"] // ❌ Creates empty strings from multiple spaces // Using trim().split(/\s+/) " hello world test ".trim().split(/\s+/) // Result: ["hello", "world", "test"] // ✅ Clean array with only actual words
```
8. Time complexity
		![[Pasted image 20260110124242.png]]