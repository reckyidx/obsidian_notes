#### limitation
	- Choices
	- Constraints
	- Goal

Skeleton
```
	functiion backtrack(output, input){
		if(output.length === input.length){
			output.push(value);
			return;
		}

		for(let i =0; i < input.length; i++) {
			if(match condition){
				make choice[i]
				backtrack(res, args)
				undo choice[i]
			}
			
		}
	}
```

Visual representation of loop works
```
							   []
                /               |              \
              [1]              [2]              [3]
           /      \          /     \          /     \
        [1,2]    [1,3]    [2,1]   [2,3]    [3,1]   [3,2]
          |        |        |       |        |       |
       [1,2,3]  [1,3,2]  [2,1,3] [2,3,1]  [3,1,2] [3,2,1]
```
Each leaf node represents a complete permutation. The backtracking allows us to explore all possible paths in this tree systematically.

This is how the algorithm generates all possible permutations of the input array [1,2,3] through recursive backtracking.