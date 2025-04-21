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
