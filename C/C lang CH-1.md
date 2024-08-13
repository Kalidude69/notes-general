
## Table of Contents
### - [Variables](Variables.md)
### - [Constraints](Constraints.md)
### - [Keywords and Comments](Keywords%20and%20Comments.md)


Before we start lets get on with the basics of this *boilerplate* code we write:-


```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```


### Code Explanation

```c
#include <stdio.h>
```
- **Purpose:** Includes the Standard Input Output library. Pre-processor Directive
- **Explanation:** This line tells the compiler to include the standard input-output library `stdio.h`, which is necessary for using the `printf` function to output text to the console.

```c
int main() {
```
- **Purpose:** Defines the `main` function.
- **Explanation:** The `main` function is the entry point of every C program. It’s where the execution starts. The `int` before `main` signifies that the function will return an integer value.

```c
    printf("Hello, World!\n");
```
- **Purpose:** Prints text to the console.
- **Explanation:** `printf` is a function from the `stdio.h` library used to print formatted output. `"Hello, World!\n"` is the string to be printed. `\n` is a newline character that moves the cursor to the next line after printing.

```c
    return 0;
```
- **Purpose:** Ends the `main` function.
- **Explanation:** `return 0;` indicates that the program has executed successfully. The value `0` is returned to the operating system.

```c
}
```
- **Purpose:** Closes the `main` function block.
- **Explanation:** This curly brace signifies the end of the `main` function.

### Summary
1. **`#include <stdio.h>`**: Includes necessary library for input/output functions.
2. **`int main() {`**: Starts the main function where program execution begins.
3. **`printf("Hello, World!\n");`**: Prints "Hello, World!" to the console with a newline.
4. **`return 0;`**: Ends the `main` function, returning `0` to indicate successful execution.
5. **`}`**: Closes the `main` function.

This program is a simple example to demonstrate the basic structure of a C program and how to output text to the console.