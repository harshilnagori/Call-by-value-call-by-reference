# Call-by-value-call-by-reference


# Pointer Operations in C++

## Aim  
To study and implement Pointer Operations (Call by Value and Call by Reference).

## Software Used  
- Visual Studio Code (VS Code)  

## Objective  
- To understand the concept of pointers in C++.  
- To differentiate between **Call by Value** and **Call by Reference**.  
- To implement pointer-based function calls.  

## Theory  

In C++, **functions** are used to perform specific tasks. When values are passed to functions, they can be passed in two ways: **Call by Value** and **Call by Reference**.  

### 1. Call by Value  
- In this method, the actual value of the argument is copied into the formal parameter of the function.  
- Any modification made inside the function affects only the copy, not the original variable.  
- It is safe because the original data remains unchanged, but it can be inefficient for large data structures since copies need to be created.  

Example in real life: giving someone a **photocopy** of a document. They can write on it, but your original document stays safe.  

### 2. Call by Reference (using Pointers)  
- In this method, instead of passing a copy, the **address (memory location)** of the variable is passed to the function.  
- Inside the function, pointers are used to directly access and modify the original data.  
- Any change made inside the function reflects back in the original variables.  
- This method is memory efficient and is commonly used when large data structures need to be manipulated without duplication.  

Example in real life: giving someone the **original document**. If they make changes, the original gets updated.  

### Why Use Pointers in Call by Reference?  
- Pointers allow direct access to memory, making programs faster and memory-efficient.  
- They help in implementing data structures like linked lists, trees, and graphs.  
- They are essential in system programming, dynamic memory allocation, and hardware-level coding.  

### Key Differences  

| Feature              | Call by Value | Call by Reference |
|----------------------|--------------|-------------------|
| Data Passed          | Copy of variable | Address of variable |
| Changes Affect       | Only local copy | Original variable |
| Memory Usage         | More (extra copy) | Less (no extra copy) |
| Safety               | Safer (original unchanged) | Riskier (original can change) |
| Speed                | Slower for large data | Faster (no copying needed) |

## Program (Combined Example)  

```cpp
#include <iostream>
using namespace std;

// Call by Value
void swapValue(int a, int b) {
    int temp = a;
    a = b;
    b = temp;
    cout << "Inside function (Call by Value): a = " << a << ", b = " << b << endl;
}

// Call by Reference (using pointers)
void swapReference(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
    cout << "Inside function (Call by Reference): a = " << *a << ", b = " << *b << endl;
}

int main() {
    int x = 10, y = 20;

    cout << "Original values: x = " << x << ", y = " << y << endl;

    // Call by Value
    swapValue(x, y);
    cout << "After Call by Value: x = " << x << ", y = " << y << endl;

    // Call by Reference
    swapReference(&x, &y);
    cout << "After Call by Reference: x = " << x << ", y = " << y << endl;

    return 0;


SAMPLE OUTPUT:

          Pass by value code-
                        a is:5
                        b is:2
                        
          Pass by pointer:
                        Original value of a is:5
                        original value of b is:2
                        Swapped value of a is:2
                        Swapped value of b is:5 

          Call by reference:
                        Original value of a is:12
                        original value of b is:21
                        Swapped value of a is:21
                        Swapped value of b is:12

         Array modification:
                        Enter a number: 4
                        Before update: 10 20 30 40 50 
                        After update: 4 5 6 7 8 

        Salary increment using pointer:
                        Enter the number of recent projects: 7
                        How many research publications have you done? 5
                        How much profit have you made in last one year? 20k
                        Enter the number of new projects in pipeline: 
                        Sorry! You did not meet the selection criteria.


CONCLUSION:

        Call by Value: Only copies of variables are passed → original data remains unchanged.
        Call by Reference: Memory addresses are passed → original data can be modified.
        Pointers are a powerful feature in C++ that allow direct memory access, efficient data manipulation, and implementation of advanced data structures.
}

