### Linear Search - Basic Introduction

**Linear search** is a simple search algorithm used to find an element in a list or array by checking each element one by one in a sequential manner.

#### Key Points:

1. **How it works**:
    
    - Start at the first element of the list.
    - Compare each element with the target value (the value you're searching for).
    - If a match is found, return the index of the matching element.
    - If no match is found after checking all elements, return an indication that the element is not present (e.g., return `-1`).
2. **Best Case**:
    
    - If the target element is at the first position, only 1 comparison is needed.
    - Time Complexity: **O(1)**.
3. **Worst Case**:
    
    - If the target element is at the last position or not present at all, you need to check all elements.
    - Time Complexity: **O(n)**, where `n` is the number of elements in the list.
4. **Use cases**:
    
    - Linear search is often used for unsorted or small datasets where more complex algorithms (like binary search) are not practical.
Basic example in C++:
```cpp
int linear_search(int A[],int n,int x){
	int i;

	for(i = 0;i < n;i++){
		if(A[i]==x){
			return i;
		}
	}
	i = -1;
	return i;
}
```
#### Pros:

- Simple to implement.
- Works on both sorted and unsorted data.

#### Cons:

- Inefficient for large datasets compared to other search algorithms like binary search.