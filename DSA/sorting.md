
#### Comparision sorting
1. Selection sort
```
for (let i = 0; i< arr.length - 1;i++){
  let minValueStoredIndex = i;
  for(let j = i+1; j < arr.length; j++){
    if(arr[j] < arr[minValueStoredIndex]){
      minValueStoredIndex = j
    }
  }

  let temp = arr[i];
  arr[i] = arr[minValueStoredIndex];
  arr[minValueStoredIndex] = temp
}
```
2. bubble sort
   Repeatedly swapping adjacent elements. Not suitable for large data sets and time complexity is quite high
```
  const bubbleSort = (arr, n) => {
  if (n === 1) {
    return
  }
  let swapped = false
  for (let i = 0; i < n - 1; i++) {
    if (arr[i] > arr[i + 1]) {
      let temp = arr[i];
      arr[i] = arr[i + 1];
      arr[i + 1] = temp
      swapped = true
    }
  }
  if (!swapped) return arr;
  return bubbleSort(arr, n - 1)
}
```
	 Time complexity o(n*n)
3. Insertion sort
		From unsorted array each element inserted into correct sorted list 
4. Merge Sort
		Its a stable sorting algorithm which means it maintains relative order of input array. worst case is **O(N logN)** . Suitable to sort on large dataset
		independently merge subarrays that makes it suitable for parallel processing.
		Cons - it requires more memory space to sort the array. 
5. Quick sort
     TC - n log n
     SC - o(1)
     take a pivot element (either first or last or median or random), iterate with rest of the elements, move smaller to left and larger to right
 6. Quick Select
		 Similar to quick sort implementation. Role is to find k th element leaving array unsorted
	


#### Non Comparision sorting

#### hybrid sorting
#### Graph-based dependency sort

it orders(linear sorting) based on directed cyclic graphs
1. Topological Sort
		Used for task A be done before task B. eg:- task scheduling, build system and resolve dependency
		- Kahn algorithm
		- DFS based topological sort
		 
