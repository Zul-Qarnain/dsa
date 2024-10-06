### Bubble Sort - Basic Introduction

**Bubble Sort** is a simple comparison-based sorting algorithm. It repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order. This process is repeated until the list is sorted.

#### Key Points:

1. **How it works**:
    
    - Start at the beginning of the array and compare the first two elements.
    - If the first element is larger than the second, swap them.
    - Move to the next pair of elements and repeat the process until the end of the array.
    - After each full pass through the array, the largest element "bubbles up" to its correct position at the end.
    - The process is repeated for the unsorted portion of the array until the entire array is sorted.
2. **Best Case**:
    
    - If the array is already sorted, only one full pass is needed.
    - Time Complexity: **O(n)** (with an optimisation to stop early if no swaps are made in a pass).
3. **Worst Case**:
    
    - The worst-case scenario occurs when the array is sorted in reverse order.
    - Time Complexity: **O(n²)** due to repeated comparisons and swaps.
4. **Space Complexity**:
    
    - **O(1)**: Like selection sort, bubble sort is an **in-place sorting algorithm**, meaning it uses no additional memory beyond a few variables.

Example in  C++: 
```cpp
#include <iostream>
using namespace std;

void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        bool swapped = false;  // To check if any swapping occurred
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                // Swap adjacent elements if they are in the wrong order
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
                swapped = true;  // Set swapped to true if swapping happens
            }
        }
        // If no two elements were swapped, the array is already sorted
        if (!swapped) {
            break;
        }
    }
}

int main() {
    int arr[] = {64, 34, 25, 12, 22, 11, 90};
    int n = sizeof(arr) / sizeof(arr[0]);
    
    bubbleSort(arr, n);

    cout << "Sorted array: \n";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }
    return 0;
}
```

#### How the example works:

- In each pass through the array, adjacent elements are compared and swapped if they are out of order.
- After each pass, the largest unsorted element is moved to its correct position.
- The inner loop gradually reduces its range as the larger elements "bubble up" to the correct position at the end of the array.

#### Pros:

- Simple and easy to understand.
- Best case time complexity of **O(n)** if the array is already sorted.

#### Cons:

- Inefficient for large datasets with a worst-case time complexity of **O(n²)**.
- Even optimised versions, which stop early when no swaps are made, still perform poorly compared to more advanced algorithms.

Bubble sort is mainly used for educational purposes to teach sorting principles, but it is generally outperformed by more efficient sorting algorithms like merge sort or quicksort for larger datasets.