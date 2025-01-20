
---
[[C lang CH-1]]
### 1. **What is the difference between compiler and interpreter?**

**Compiler vs. Interpreter:**

- **Compiler**:
    
    - Translates the entire source code into machine code before execution.
    - Produces a separate executable file.
    - Errors are reported after the entire code is compiled.
    - Execution is faster because the code is precompiled.
    - Example: C, C++.
- **Interpreter**:
    
    - Translates and executes code line-by-line.
    - No separate executable file is created.
    - Errors are reported immediately when encountered.
    - Execution is slower since translation happens at runtime.
    - Example: Python, JavaScript.

**In short**, compilers pre-compile the whole program, while interpreters execute it on the fly.

---

### 2. **What is the difference between high-level and low-level languages?**

**Difference Between High-Level and Low-Level Languages:**

- **High-Level Language**:
    
    - Close to human language and easy to read, write, and understand.
    - Requires a compiler or interpreter to convert to machine code.
    - Examples: C, Python, Java.
    - Portable across different platforms (platform-independent).
    - Focuses on problem-solving and abstraction rather than hardware.
- **Low-Level Language**:
    
    - Close to machine language and hard for humans to understand.
    - Requires no or minimal translation (assembly language needs an assembler).
    - Examples: Machine Code, Assembly Language.
    - Platform-dependent and specific to the hardware.
    - Provides greater control over hardware and memory management.

**In short**, high-level languages are user-friendly and portable, while low-level languages are machine-oriented and efficient for hardware-specific tasks.

---

### 3. **What is a header file?**

A **header file** in C is a file with a `.h` extension that contains declarations of functions, macros, constants, and types. It allows code reuse by providing predefined functionalities or declarations that can be included in multiple programs using the `#include` directive. For example, `stdio.h` provides declarations for input/output functions like `printf()` and `scanf()`.

---

### 4. **# is called as a preprocessor directive. What does it mean?**

A **preprocessor directive** starts with `#` and is processed before compilation. It instructs the compiler to include files (`#include`), define constants (`#define`), or handle conditional compilation. Example: `#include <stdio.h>` includes the input/output library. It ensures modularity and preparation for compilation.

---

### 5. **Different data types in C with sizes of each.**

|**Data Type**|**Description**|**Size**|**Example**|
|---|---|---|---|
|`int`|Integer|4 bytes|`int x = 5;`|
|`char`|Character|1 byte|`char c = 'a';`|
|`float`|Floating Point|4 bytes|`float f = 3.14;`|
|`double`|Double Precision|8 bytes|`double d = 3.14159;`|
|`void`|No value|-|`void *ptr;`|
|`unsigned int`|Unsigned Integer|4 bytes|`unsigned int ui = 5;`|
|`long`|Long Integer|8 bytes|`long l = 123456789;`|
|`short`|Short Integer|2 bytes|`short s = 100;`|
|`long long`|Long Long Integer|8 bytes|`long long ll = 123456789012;`|
|`unsigned long`|Unsigned Long|8 bytes|`unsigned long ul = 5;`|
|`enum`|Enumeration|-|`enum color { red, green, blue };`|
|`struct`|Structure|-|`struct point { int x, y; };`|
|`union`|Union|-|`union data { int i; float f; };`|

---

### 6. **What are the different types of operators present in C?**

|**Operator Type**|**Description**|**Example**|
|---|---|---|
|Arithmetic|Performs basic arithmetic operations|`+`, `-`, `*`, `/`, `%`|
|Relational|Compares two values|`==`, `!=`, `<`, `>`, `<=`, `>=`|
|Logical|Combines or inverts conditions|`&&`, `|
|Bitwise|Operates on bits of data|`&`, `|
|Assignment|Assigns values to variables|`=`, `+=`, `-=`, `*=`, `/=`, `%=`|
|Increment/Decrement|Increases or decreases value by 1|`++`, `--`|
|Conditional|Returns value based on condition|`?:`|
|Special|Includes special operations|`sizeof`, `&`, `*`, `->`|

---

### 7. **Different storage classes in C:**

In C, storage classes define the scope, lifetime, and visibility of variables. The four main types are:

1. **auto**:
    
    - Default storage class for local variables.
    - Local to the block or function where declared.
    - Lifetime is limited to the duration of the function or block.
2. **register**:
    
    - Used for variables that are frequently accessed.
    - Suggests to the compiler to store the variable in CPU registers for faster access.
    - Typically applies to local variables.
    - Cannot be used with the `&` (address-of) operator.
3. **static**:
    
    - Retains the value of a variable between function calls.
    - Used for variables inside functions or at the file level.
    - At the function level, it preserves the variable's state between function calls.
    - At the file level, it restricts visibility to that file.
4. **extern**:
    
    - Indicates that a variable is defined elsewhere (outside the current file).
    - Used to declare global variables that are defined in another file.
    - Extends the scope of the variable across multiple files.

---

### 8. **What is the difference between switch case and conditional statements?**

**Switch-Case vs. Conditional Statements:**

- **Switch-Case**:
    
    - Used to select one of many code blocks to execute based on the value of a single expression.
    - Faster when comparing multiple values for one variable.
    - Works with integer, character, and enumerated types.
- **Conditional Statements (if-else)**:
    
    - Used for decision-making based on one or more conditions.
    - More flexible, can handle complex conditions (comparisons, logical operations).
    - Works with any type of condition (boolean, relational).

**In short**, `switch-case` is simpler and faster for checking multiple fixed values of one variable, while `if-else` is more flexible for complex conditions.

---

### 9.**What is fall-through in switch-case?**

In C, **fall-through** refers to the behavior where, when a `case` in a `switch` statement does not have a `break` statement, the control "falls through" to the next `case`. This means the code in the following `case` block will execute unless it has its own `break` statement.

### Example of fall-through:

``` c 

switch (x) {
    case 1:
        printf("One\n");
    case 2:
        printf("Two\n");
    case 3:
        printf("Three\n");
        break;
    default:
        printf("Default\n");
}
```

This happens because there's no `break` after `case 1`, so the control falls through to `case 2` and then to `case 3`, where it prints all subsequent outputs until a `break` is encountered.

### Why fall-through occurs:

- By default, the `switch` statement in C doesn't automatically stop execution after a match is found. If you don't explicitly use a `break`, the control will proceed to the next `case`.
- This behavior allows you to execute multiple cases together without repeating the same code.

### 10. **What type of values are supported by switch?**

In C, the `switch` statement supports the following types of values:

1. **Integer types**:
    
    - `int`, `char`, `short`, `long`, etc.
2. **Enumerated types**:
    
    - `enum` values can be used in a `switch`.
3. **Character literals**:
    
    - Characters are treated as integer values (ASCII values).

**Note**: `switch` does not support floating-point types (`float`, `double`) or string literals directly.

---

### 11. **What is entry control and exit control?**

**Entry Control vs. Exit Control:**

- **Entry Control**:
    
    - The condition is checked **before** entering the loop or block.
    - If the condition is false, the loop/block may not execute.
    - Examples: `for`, `while` loops.
- **Exit Control**:
    
    - The condition is checked **after** executing the loop/block at least once.
    - The loop/block always executes at least once, even if the condition is initially false.
    - Example: `do-while` loop.

**In short**, entry control checks the condition first (may skip execution), while exit control ensures the loop/block executes at least once.

---

### 12. **What is difference between break and continue statement ? What is jump statement?**


**Difference between `break` and `continue` statements:**

- **`break`**:
    
    - Exits the loop or switch statement immediately.
    - Skips the remaining iterations or cases and moves to the next statement after the loop or switch.
    - Example: Exits a `for`, `while`, or `switch` statement.
- **`continue`**:
    
    - Skips the current iteration of the loop and moves to the next iteration.
    - Does not exit the loop; it just continues with the next cycle.
    - Example: Skips to the next iteration in a `for` or `while` loop.

---

**Jump Statement:**

A **jump statement** in C is used to transfer control unconditionally from one part of the program to another. The primary jump statements are:

- **`break`**: Exits a loop or switch.
- **`continue`**: Skips the current iteration of a loop.
- **`goto`**: Transfers control to a labeled statement in the program. It can be used to jump to another part of the code.
---

### 13. **What do you mean by infinite loop?

**Infinite Loop:**

An **infinite loop** is a loop that never terminates because its condition is always true or it lacks a termination condition. This can occur unintentionally if the loop's exit condition is never met. Infinite loops can be useful in certain situations, such as waiting for user input or running servers, but they can also cause the program to hang if not controlled properly.

**Example:**

```c
while(1) {  // Always true, infinite loop
    printf("This loop will run forever\n");
}
```

---

### 14. **What do you mean by user defined function ?

**User-Defined Functions:**

A **user-defined function** is a function created by the programmer to perform a specific task. It can be called multiple times in the program, making the code more modular and reusable. User-defined functions can take inputs (parameters) and return outputs (values). They allow breaking down a large program into smaller, manageable sections.

**Example:**

```c
#include <stdio.h>

void greet() {  // User-defined function
    printf("Hello, User!\n");
}

int main() {
    greet();  // Function call
    return 0;
}
```

In this example, `greet()` is a user-defined function.

---

### **15. If a function starts with "int" then what does it signify?**

If a function starts with `int`, it signifies that the function **returns an integer value**. The `int` is the return type of the function, meaning that when the function finishes executing, it will provide an integer result to the part of the program that called it.

**Example:**

```c
int add(int a, int b) {
    return a + b;  // Returns the sum as an integer
}

int main() {
    int result = add(5, 3);  // Calls the add function
    printf("Sum: %d\n", result);  // Prints the result
    return 0;
}
```

In this example, `add()` is a function that takes two integers as parameters and returns their sum as an integer (`int`).

---


### **16. What do you mean by function prototype?**

A **function prototype** in C is a declaration of a function that provides the compiler with information about the function's name, return type, and parameters before the function is actually defined. It allows the function to be called before its full definition in the code. A prototype helps in type-checking during compilation and enables the compiler to ensure the function is used correctly.

**Syntax:**

```c
return_type function_name(parameter_list);
```

**Example:**

```c
#include <stdio.h>

// Function prototype
int add(int, int);

int main() {
    int result = add(5, 3);  // Function call
    printf("Sum: %d\n", result);
    return 0;
}

// Function definition
int add(int a, int b) {
    return a + b;
}
```

In this example, `int add(int, int);` is the function prototype, indicating that the function `add` will return an integer and accept two integer parameters.

---
### **17. Explain what do you mean by function signature?**

A **function signature** in C refers to the combination of the function's **name** and its **parameter types**. It uniquely identifies a function within a program, and it is used to distinguish functions from one another, especially when there are multiple functions with the same name but different parameters (function overloading is not supported in C, but parameter lists can differ).

The function signature does **not** include the return type.

**Components of a function signature:**

- **Function name**: The name of the function.
- **Parameter types**: The types of parameters that the function accepts (without their names).

**Example:**

```c
int add(int, int);  // Function signature: name is 'add' and it takes two integers
```

Here, `add(int, int)` is the function signature because it specifies that `add` takes two `int` parameters, but the names of the parameters are not required in the signature.

---

### **18. What is call by value and call by reference ?**


**Call by Value vs Call by Reference**:

- **Call by Value**:
    
    - In this method, a copy of the actual argument is passed to the function.
    - Changes made to the parameter inside the function do not affect the original argument.
    - It provides security because the actual data remains unaffected.
    - **Example:**
    
    ```c
    void function(int x) {
        x = 10;  // Only the local copy of x is changed
    }
    ```
    
- **Call by Reference**:
    
    - In this method, the address (reference) of the actual argument is passed to the function.
    - Changes made to the parameter inside the function directly affect the original argument.
    - It allows functions to modify the actual data.
    - **Example:**
    
    ```c
    void function(int *x) {
        *x = 10;  // The actual variable is changed
    }
    ```


---

### **19. What happens when a `return` statement is encountered in a function?**


When a `return` statement is encountered in a function, the following happens:

- **Function execution stops**: The `return` statement immediately terminates the function’s execution, and control is transferred back to the calling function.
- **Return value is passed back (if any)**: If the function has a return type (e.g., `int`), the value specified in the `return` statement is passed back to the calling function.
- **Memory cleanup**: After returning, any local variables used in the function are destroyed, and memory is freed (depending on the storage class of the variable).

**Example:**

```c
int add(int a, int b) {
    return a + b;  // Terminates function and returns the sum
}

int main() {
    int result = add(5, 3);  // Function call, result is 8
    return 0;
}
```

In this example, when the `return a + b;` is encountered in the `add` function, it ends the function and sends the value of `a + b` back to `main`.

---

### **20. What is recursion ?**

**Recursion** in C is a programming technique where a function calls itself to solve a problem. The function breaks the problem into smaller instances of the same problem, and continues to call itself until a base condition is met, which stops the recursion.

Key points about recursion:

- **Base case**: A condition that prevents infinite recursion, ensuring that the function eventually stops.
- **Recursive case**: The part where the function calls itself with modified arguments to progress toward the base case.

**Example:**

```c
#include <stdio.h>

int factorial(int n) {
    if (n == 0)  // Base case
        return 1;
    else
        return n * factorial(n - 1);  // Recursive call
}

int main() {
    int result = factorial(5);  // Calling the recursive function
    printf("Factorial: %d\n", result);
    return 0;
}
```

In this example, the `factorial` function calls itself until `n == 0` (base case), after which it returns the result.

---


### **21. In recursion do the following programs.**

- *Fibonacci series*
- *Print natural No*
- *Factorial*

1. Fibonacci Series (Recursive)
``` c

#include <stdio.h>

int fibonacci(int n) {
    if (n <= 1)
        return n;
    else
        return fibonacci(n-1) + fibonacci(n-2);
}

int main() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    printf("Fibonacci series up to %d: ", num);
    for (int i = 0; i <= num; i++) {
        printf("%d ", fibonacci(i));
    }
    return 0;
}
```



2. Print Natural Numbers (Recursive)

``` c
 #include<stdio.h>

void natty(int x) {
   if (x == 0)
       return; // End recursion
   printf("%d \n", x);
   natty(x - 1);
}

void nat(int x) {
   if (x > 0) {
       printf("%d \t", x);
       nat(x - 1);
   }
}

int main() {
   int n;
   printf("Enter the number: ");
   scanf("%d", &n);
   printf("\n");
   nat(n);
   printf("\n");
   return 0;
}

```


3. Factorial (Recursive)

``` c
#include <stdio.h>

int factorial(int n) {
    if (n == 0 || n == 1) 
        return 1;
    return n * factorial(n - 1);
}

int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    printf("Factorial of %d is %d", n, factorial(n));
    return 0;
}

```

---

### **22. What is default values in a function?**

**Default values in functions**:  
Default values are pre-defined values assigned to function parameters. If no argument is provided for a parameter when the function is called, the default value is used.

Example:

``` c
#include <stdio.h>

// Not natively supported in C, this is just a workaround with default values.
int add(int a, int b) { 
    return a + b; 
}

int main() {
    printf("%d", add(5, 10)); // Uses default values
    return 0;
}

```

---
### **23. What is actual parameter and formal parameter in a function?**

**Actual Parameter**:  
The values or variables passed to a function during a function call. These are the "inputs" provided to the function.  
Example:

```c
int sum(int a, int b); // Function prototype
sum(10, 20); // Here, 10 and 20 are actual parameters
```

**Formal Parameter**:  
The variables defined in the function declaration or definition to receive the actual parameters. They act as placeholders within the function.  
Example:

```c
int sum(int a, int b) { // Here, `a` and `b` are formal parameters
    return a + b;
}
```

**In short**: Actual parameters are the values passed by the caller, while formal parameters are the placeholders defined by the function.

---

### **24. What is the benefit of structure ?**

**Benefits of Structure in C**:

- **Organizes Data**: Groups related variables (of different types) under one name, making programs more organized and readable.
- **Reusability**: Structures can be reused in multiple parts of a program or other programs, enhancing code modularity.
- **Memory Management**: Allows storing complex data logically without needing separate variables for each element.
- **Ease of Access**: Makes handling related data simpler using a single entity.
- **Foundation for Advanced Concepts**: Structures form the basis for creating complex data structures like linked lists, trees, and objects.

**Example**:

```c
struct Student {
    int id;
    char name[50];
    float marks;
}; // Combines different types of data under one entity.
```

---

### **25. Using structure create a Student data-type.**

``` c
#include<stdio.h>
typedef struct Structure_students{
  char name[30],dept[30],sub[30];
  int marks;
}stu_info;
void main(){
  stu_info x[4];
  int i;
  for(i=0;i<4;i++)
  {
    printf("Enter the details of the %d student\n",i+1);
    scanf("%s%s%s%d",x[i].name,x[i].dept,x[i].sub,&x[i].marks);
  }
  for(i=0;i<4;i++)
  {
    printf("\n Value of %d student name %s Department %s subject %s Marks %d",i+1,x[i].name,x[i].dept,x[i].sub,x[i].marks);
    printf("\n");
  }
}
```

---

### **26. What is a pointer ? How can you store the address of an integer variable in a pointer variable?**

**Pointer in C**:  
A pointer is a variable that stores the memory address of another variable. It provides an efficient way to access and manipulate data in memory.

**Storing Address of an Integer Variable in a Pointer**:

To store the address of an integer variable in a pointer:

1. Declare an integer pointer using `int *`.
2. Use the address-of operator (`&`) to get the address of the integer variable.
3. Assign this address to the pointer.

**Example**:

```c
#include <stdio.h>

int main() {
    int num = 10;       // Integer variable
    int *ptr = &num;    // Pointer storing the address of num

    printf("Value of num: %d\n", num);
    printf("Address of num: %p\n", ptr);
    printf("Value at the address stored in ptr: %d\n", *ptr);

    return 0;
}
```

In this example:

- `ptr` holds the address of `num`.
- `*ptr` dereferences the pointer to access the value of `num`.

---
### **27. How can you create a dynamic array using pointer ?**


**Dynamic Array Using Pointer in C**:  
A dynamic array is an array whose size is determined at runtime. In C, dynamic arrays can be created using pointers and memory allocation functions like `malloc()` or `calloc()`.

### Steps to Create a Dynamic Array:

1. Declare a pointer.
2. Allocate memory using `malloc()` or `calloc()`.
3. Access array elements using the pointer.
4. Free the allocated memory using `free()` when done.

### Example:

```c
#include <stdio.h>
#include <stdlib.h> // For malloc and free

int main() {
    int *arr;  // Pointer for dynamic array
    int size, i;

    // Specify the size of the array
    printf("Enter the size of the array: ");
    scanf("%d", &size);

    // Allocate memory for the array
    arr = (int *)malloc(size * sizeof(int));
    if (arr == NULL) {  // Check if memory allocation was successful
        printf("Memory allocation failed!\n");
        return 1;
    }

    // Input values into the array
    printf("Enter %d elements:\n", size);
    for (i = 0; i < size; i++) {
        scanf("%d", &arr[i]);
    }

    // Print the array elements
    printf("The elements of the array are:\n");
    for (i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    // Free the allocated memory
    free(arr);

    return 0;
}
```

### Key Points:

- **`malloc()`**: Allocates memory of specified size. Returns `NULL` if allocation fails.
- **Accessing Elements**: Use `arr[i]` to access elements.
- **Free Memory**: Always use `free()` to release the allocated memory to prevent memory leaks.

---

### **28. What is the benefit of an array ?**

### **Benefits of Using Arrays in C**:

1. **Efficient Data Management**:
    
    - Arrays allow storing multiple values of the same data type in a single variable, reducing the need for multiple variables.
2. **Random Access**:
    
    - Array elements can be accessed directly using an index, making data retrieval faster.
3. **Memory Utilization**:
    
    - Arrays provide a contiguous block of memory, which is more memory-efficient than using multiple variables.
4. **Simplified Code**:
    
    - Arrays reduce code complexity when working with large datasets by enabling operations like loops for data processing.
5. **Ease of Sorting and Searching**:
    
    - Arrays make it easier to implement algorithms for sorting and searching, such as bubble sort or binary search.
6. **Static and Dynamic Sizes**:
    
    - Arrays can have a fixed size (static arrays) or dynamic size (using pointers), allowing flexibility based on requirements.
7. **Supports Multidimensional Data**:
    
    - Arrays can represent multi-dimensional data (e.g., matrices) for complex computations.
8. **Data Grouping**:
    
    - Arrays are ideal for grouping related data, such as storing marks of students or monthly sales data.

### Example:

Instead of:

```c
int a1, a2, a3, a4, a5; // Five separate variables
```

Use:

```c
int arr[5]; // Single array to store 5 values
```

---

### **29. What is the disadvantage of an array ?**


### **Disadvantages of Using Arrays in C**:

1. **Fixed Size**:
    
    - The size of an array is defined at compile time and cannot be changed dynamically (for static arrays). This can lead to memory wastage or insufficient storage.
2. **No Bounds Checking**:
    
    - Accessing elements beyond the array's bounds can result in undefined behavior, causing bugs or crashes.
3. **Single Data Type**:
    
    - Arrays can only store elements of the same data type, limiting flexibility when handling heterogeneous data.
4. **Insertion/Deletion Overhead**:
    
    - Adding or removing elements in the middle of an array requires shifting elements, which is time-consuming.
5. **Memory Inefficiency**:
    
    - For large arrays, significant memory is allocated upfront, which may not always be fully utilized.
6. **Lack of Flexibility**:
    
    - Arrays do not support advanced operations like dynamic resizing, which is available in other data structures like linked lists or vectors.
7. **No Built-in Functions**:
    
    - Unlike modern programming languages, C arrays lack built-in functions for operations like sorting, searching, or resizing, requiring manual implementation.

---
### **30. What will be starting and ending index for an array with n element ?**

In C, array indexing is **zero-based**, meaning:

- The **starting index** is `0`.
- The **ending index** is `n-1`, where `n` is the total number of elements in the array.

**Example**:  
For an array of size 5 (`int arr[5]`):

- Starting index = `0`
- Ending index = `5 - 1 = 4`

---

### **31. In an array, the array block will be stored in continuous memory locations. Explain.**

In C, arrays are stored in **contiguous memory locations**, meaning all elements are placed sequentially in memory, one after the other.

- **How it works**:  
    The array's starting address (base address) points to the memory location of the first element. Each subsequent element is stored in the next memory block based on the size of the data type.
    
- **Example**:  
    For `int arr[3] = {10, 20, 30}`, if the base address is `1000`:
    
    - `arr[0]` is stored at `1000`
    - `arr[1]` is stored at `1004` (since `int` is 4 bytes)
    - `arr[2]` is stored at `1008`

**Benefits**:

1. Efficient element access using index calculations: `Address = Base + (Index × Size of data type)`.
2. Improves performance for operations like iteration or searching.

---

### **32.A Using arrays perform these programs**

#### 1. **Searching an Element in an Array (Linear Search)**

```c
#include <stdio.h>
int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int n = 5, search = 30, found = 0;
    for (int i = 0; i < n; i++) {
        if (arr[i] == search) {
            found = 1;
            printf("Element %d found at index %d\n", search, i);
            break;
        }
    }
    if (!found) {
        printf("Element not found\n");
    }
    return 0;
}
```

---

#### 2. **Binary Search**

```c
#include <stdio.h>
int binarySearch(int arr[], int n, int search) {
    int low = 0, high = n - 1, mid;
    while (low <= high) {
        mid = (low + high) / 2;
        if (arr[mid] == search) return mid; // Element found
        else if (arr[mid] < search) low = mid + 1; // Search in right half
        else high = mid - 1; // Search in left half
    }
    return -1; // Element not found
}

int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int n = 5, search = 30;
    int result = binarySearch(arr, n, search);
    if (result != -1) printf("Element %d found at index %d\n", search, result);
    else printf("Element not found\n");
    return 0;
}
```

---

#### 3. **Linear Search**

``` c
#include <stdio.h>
int linearSearch(int arr[], int n, int search) {
    for (int i = 0; i < n; i++) {
        if (arr[i] == search) return i; // Element found
    }
    return -1; // Element not found
}

int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int n = 5, search = 40;
    int result = linearSearch(arr, n, search);
    if (result != -1) printf("Element %d found at index %d\n", search, result);
    else printf("Element not found\n");
    return 0;
}
```


---

### **32.B Solve these questions on Sorting**

#### 1. **Bubble Sort**

```c
#include <stdio.h>
void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) { // Swap
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}
int main() {
    int arr[] = {5, 2, 9, 1, 5};
    int n = 5;
    bubbleSort(arr, n);
    for (int i = 0; i < n; i++) printf("%d ", arr[i]);
    return 0;
}
```

---

#### 2. **Selection Sort**

```c
#include <stdio.h>
void selectionSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        int minIdx = i;
        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[minIdx]) minIdx = j;
        }
        int temp = arr[minIdx];
        arr[minIdx] = arr[i];
        arr[i] = temp;
    }
}
int main() {
    int arr[] = {5, 2, 9, 1, 5};
    int n = 5;
    selectionSort(arr, n);
    for (int i = 0; i < n; i++) printf("%d ", arr[i]);
    return 0;
}
```

---

#### 3. **Insertion Sort**

```c
#include <stdio.h>
void insertionSort(int arr[], int n) {
    for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
}
int main() {
    int arr[] = {5, 2, 9, 1, 5};
    int n = 5;
    insertionSort(arr, n);
    for (int i = 0; i < n; i++) printf("%d ", arr[i]);
    return 0;
}
```

---

#### 4. **Maximum and Minimum Element in an Array**

```c
#include <stdio.h>
int main() {
    int arr[] = {5, 2, 9, 1, 5};
    int n = 5, max = arr[0], min = arr[0];
    for (int i = 1; i < n; i++) {
        if (arr[i] > max) max = arr[i];
        if (arr[i] < min) min = arr[i];
    }
    printf("Maximum: %d, Minimum: %d\n", max, min);
    return 0;
}
```

---

#### 5. **Sum of an Array**

``` c
#include <stdio.h>
int main() {
    int arr[] = {5, 2, 9, 1, 5};
    int n = 5, sum = 0;
    for (int i = 0; i < n; i++) sum += arr[i];
    printf("Sum of array: %d\n", sum);
    return 0;
}
```

---

### **33. In File Handling: How to Open a File and Read the Contents**

To open a file and read its contents in C, use the following steps:

#### Code Example

```c
#include <stdio.h>

int main() {
    FILE *file;                  // Declare a file pointer
    char ch;

    file = fopen("example.txt", "r"); // Open the file in read mode
    if (file == NULL) {               // Check if the file exists
        printf("Error: File not found.\n");
        return 1;
    }

    printf("File contents:\n");
    while ((ch = fgetc(file)) != EOF) { // Read the file character by character
        putchar(ch);                   // Print each character to the console
    }

    fclose(file);                      // Close the file
    return 0;
}
```

#### Explanation

1. **`FILE *file`**: Declares a pointer to handle the file.
2. **`fopen()`**: Opens the file in a specific mode (`"r"` for reading).
3. **`fgetc()`**: Reads one character at a time from the file.
4. **`EOF`**: End of file condition.
5. **`fclose()`**: Closes the file after reading.

---

#### Key Points:

- Use `"r"` mode to read files.
- Always check if the file pointer is `NULL` to avoid runtime errors.
- `fgetc()` reads character by character, and `fgets()` reads a full line.

----


