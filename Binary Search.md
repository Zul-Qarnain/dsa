### Binary Search - Basic Introduction

**Binary search** is an efficient search algorithm that works on sorted arrays or lists. It repeatedly divides the search interval in half to find the target value.

#### Key Points:

1. **How it works**:
    
    - Begin by comparing the middle element of the array with the target value.
    - If the target is equal to the middle element, the search ends.
    - If the target is smaller than the middle element, repeat the search in the left half.
    - If the target is larger, repeat the search in the right half.
    - This process continues until the target is found or the search interval is empty.
2. **Best Case**:
    
    - If the target element is the middle element in the first comparison.
    - Time Complexity: **O(1)**.
3. **Worst Case**:
    
    - When the search space is divided down to a single element.
    - Time Complexity: **O(log n)**, where `n` is the number of elements.
4. **Prerequisite**:
    
    - The array must be **sorted** for binary search to work.
Example in C++:
```cpp
#include <iostream>
using namespace std;

int binarySearch(int arr[], int size, int target) {
    int left = 0, right = size - 1;
    
    while (left <= right) {
        int mid = left + (right - left) / 2;  // Calculate the middle element

        if (arr[mid] == target)
            return mid;  // Target found, return the index

        if (arr[mid] < target)
            left = mid + 1;  // Target is in the right half
        else
            right = mid - 1;  // Target is in the left half
    }
    
    return -1;  // Target not found
}

int main() {
    int arr[] = {2, 3, 4, 10, 40};
    int size = sizeof(arr) / sizeof(arr[0]);
    int target = 10;
    int result = binarySearch(arr, size, target);
    
    if(result == -1)
        cout << "Element is not present in array";
    else
        cout << "Element is present at index " << result;
    
    return 0;
}

```

#### Pros:

- Much more efficient than linear search, especially for large datasets.
- Time complexity is **O(log n)**, which makes it suitable for large, sorted datasets.
#### Cons:

- Can only be used on **sorted** data.
- Requires more complex logic compared to linear search.