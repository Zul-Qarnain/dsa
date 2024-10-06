Recursion = a programming technique where a function invokes itself from within
break a complex concept into a repeatable single steps

             (iterative vs recursive)
        advantages = less code and is cleaner 
			        useful for sorting and searching algorithms 
		disadvantages = uses more memory
						slower 


Here is the example: 
```cpp
#include<iostream>

int main(void){
	walk(100);
}
int walk(int steps){
	std::cout<<"You have taken a step!"<<"\n";
} //Here I have used the iterative Method 

	#include <iostream>
	int main(void){
		walk(100);
	}
	void walk(int steps){
		if(steps>0){
		std::cout<<"You have taken a step!"<<"\n";
		walk(stpes--);
		}
	}
//Here I have used the recursive method 

```

		



### Recursion - Basic Introduction

**Recursion** is a programming technique where a function calls itself to solve smaller instances of the same problem until it reaches a base case.

#### Key Points:

1. **How it works**:
    - A recursive function typically consists of two parts:
        - **Base Case**: A condition where the function stops calling itself to prevent infinite recursion.
        - **Recursive Case**: The function calls itself with modified parameters, gradually reducing the problem size until it reaches the base case.
2. **Example**: **Factorial Calculation**
    - The factorial of a number `n` is `n * (n - 1) * ... * 1`.
    - Factorial of `0` is defined as `1` (this is the base case).
#### Example (C++):

```cpp
#include <iostream>
using namespace std;

int factorial(int n) {
    // Base case: if n is 0, return 1
    if (n == 0)
        return 1;
    // Recursive case: n * factorial(n - 1)
    else
        return n * factorial(n - 1);
}

int main() {
    int number = 5;
    cout << "Factorial of " << number << " is " << factorial(number) << endl;
    return 0;
}

```

#### How the example works:

- When `factorial(5)` is called:
    - It calls `factorial(4)`, which calls `factorial(3)`, and so on until `factorial(0)` is reached (base case), returning `1`.
    - The stack of calls then starts resolving, multiplying each value as it returns from the recursion.

#### Types of Recursion:

- **Direct Recursion**: A function directly calls itself (like the factorial example).
- **Indirect Recursion**: A function calls another function, which in turn calls the original function.

#### Pros:

- **Simplifies code**: Complex problems can be simplified into smaller, repeatable tasks.
- **Natural fit**: For problems that can be divided into similar subproblems (like tree traversal, sorting algorithms).

#### Cons:

- **Memory intensive**: Recursive calls consume stack space, which can lead to stack overflow for deep recursion.
- **Can be slower**: Recursion can be inefficient if not optimized, as redundant calculations may occur (e.g., in basic Fibonacci calculations).

#### Use cases:

- Problems like tree traversals, backtracking (e.g., solving mazes), and divide-and-conquer algorithms (e.g., merge sort, quicksort) are ideal for recursion.