### Selection Sort - Basic Introduction

**Selection Sort** is a simple comparison-based sorting algorithm. It works by repeatedly selecting the smallest (or largest, depending on the sorting order) element from the unsorted portion of the array and swapping it with the first unsorted element, progressively reducing the unsorted portion.

#### Key Points:

1. **How it works**:
    
    - Start with the first element as the minimum.
    - Traverse the unsorted portion of the array to find the smallest element.
    - Swap the smallest element with the first unsorted element.
    - Move the boundary between the sorted and unsorted portions one element to the right.
    - Repeat until the entire array is sorted.
2. **Best Case**:
    
    - Even in the best case (already sorted array), selection sort still makes all comparisons.
    - Time Complexity: **O(n²)**.
3. **Worst Case**:
    
    - The worst-case scenario also occurs when sorting a reversed array.
    - Time Complexity: **O(n²)**.
4. **Space Complexity**:
    
    - **O(1)**: Selection sort is an **in-place sorting algorithm**, meaning it doesn’t require extra space for sorting aside from a few variables.

Example in C++ :

```cpp
#include <iostream>
using namespace std;

void selectionSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        int minIndex = i;  // Assume the first unsorted element is the minimum
        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[minIndex]) {
                minIndex = j;  // Find the index of the minimum element
            }
        }
        // Swap the found minimum element with the first unsorted element
        int temp = arr[minIndex];
        arr[minIndex] = arr[i];
        arr[i] = temp;
    }
}

int main() {
    int arr[] = {64, 25, 12, 22, 11};
    int n = sizeof(arr) / sizeof(arr[0]);

    selectionSort(arr, n);

    cout << "Sorted array: \n";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }
    return 0;
}

```

#### How the example works:

- In the first pass, the algorithm finds the smallest element in the array and places it in the first position.
- In the second pass, it finds the second smallest element and places it in the second position, and so on.

#### Pros:

- Simple to understand and implement.
- Performs well on small datasets.

#### Cons:

- Inefficient for large datasets, with a time complexity of **O(n²)**.
- Performs the same number of comparisons regardless of whether the array is already sorted.

Selection sort is a fundamental algorithm to know, but it is generally outperformed by more efficient algorithms like quick sort or merge sort for larger datasets.