Here's a concise note about **Output** in C

---

## Output in C

**Output** in C refers to displaying data to the user, typically on the screen. The primary way to generate output in C is through the `printf()` function, which is part of the `stdio.h` library.

### 1. **`printf()` Function**
   - **Purpose**: Used to print text, variables, and results to the console.
   - **Syntax**:
     ```c
     printf("format string", variable1, variable2, ...);
     ```
   - **Format Specifiers**: These are placeholders in the format string that specify the type of data to be printed.
     - **Common Specifiers**:
       - `%d` or `%i`: Integer
       - `%c`: Character
       - `%f`: Floating-point number
       - `%s`: String
       - `%lf`: Double
       - `%x`: Hexadecimal number

   - **Example**:
     ```c
     int x = 5;
     float y = 3.14;
     printf("Integer: %d, Float: %f\n", x, y);
     ```
     - **Output**: `Integer: 5, Float: 3.140000`

### 2. **Escape Sequences**
   - **Purpose**: Used to insert special characters in the output.
   - **Common Escape Sequences**:
     - `\n`: Newline (moves cursor to the next line)
     - `\t`: Tab (inserts a horizontal tab)
     - `\\`: Backslash
     - `\"`: Double quote

   - **Example**:
     ```c
     printf("Hello, World!\n");
     printf("C Programming\tis fun!\n");
     ```
     - **Output**:
       ```
       Hello, World!
       C Programming    is fun!
       ```

### 3. **Outputting Variables**
   - You can print multiple variables and mix text with variables in a single `printf()` statement by using multiple format specifiers.

   - **Example**:
     ```c
     char name[] = "Alice";
     int age = 25;
     printf("Name: %s, Age: %d\n", name, age);
     ```
     - **Output**: `Name: Alice, Age: 25`

### 4. **Formatting Output**
   - **Width and Precision**: You can control the width and precision of the printed output.
     - `%5d`: Prints an integer with a minimum width of 5 characters.
     - `%.2f`: Prints a float with 2 decimal places.

   - **Example**:
     ```c
     float pi = 3.14159;
     printf("Pi to 2 decimal places: %.2f\n", pi);
     ```
     - **Output**: `Pi to 2 decimal places: 3.14`

---


## Input

Here's a concise note about **Input** in C, formatted for your notes:

---

## Input in C

**Input** in C refers to reading data from the user or from a file. The primary function for reading input from the console is `scanf()`, which is part of the `stdio.h` library.

### 1. **`scanf()` Function**
   - **Purpose**: Used to read formatted input from the standard input (keyboard).
   - **Syntax**:
     ```c
     scanf("format string", &variable1, &variable2, ...);
     ```
   - **Format Specifiers**: These are placeholders in the format string that match the type of the input data.
     - **Common Specifiers**:
       - `%d` or `%i`: Integer
       - `%c`: Character
       - `%f`: Floating-point number
       - `%s`: String (character array)
       - `%lf`: Double

   - **Example**:
     ```c
     int age;
     float height;
     printf("Enter your age: ");
     scanf("%d", &age);
     printf("Enter your height: ");
     scanf("%f", &height);
     ```
     - **User Input**: `25` for age, `5.9` for height
     - **Output**: 
       ```
       Enter your age: 25
       Enter your height: 5.9
       ```

### 2. **Reading Strings**
   - **Purpose**: Used to read a sequence of characters until whitespace or newline is encountered.
   - **Common Use**:
     - `%s` is used to read a string. Ensure the variable is large enough to store the input.

   - **Example**:
     ```c
     char name[50];
     printf("Enter your name: ");
     scanf("%s", name);
     ```
     - **User Input**: `Alice`
     - **Output**: `Enter your name: Alice`

### 3. **Handling Multiple Inputs**
   - You can read multiple inputs in a single `scanf()` call by specifying multiple format specifiers.

   - **Example**:
     ```c
     int day, month, year;
     printf("Enter date (day month year): ");
     scanf("%d %d %d", &day, &month, &year);
     ```
     - **User Input**: `12 8 2024`
     - **Output**: `Enter date (day month year): 12 8 2024`

### 4. **Input Validation**
   - **Purpose**: Ensures that the input matches expected types and formats.
   - **Example**:
     ```c
     int number;
     printf("Enter a number: ");
     while (scanf("%d", &number) != 1) {
         printf("Invalid input. Enter a number: ");
         while (getchar() != '\n'); // Clear invalid input
     }
     ```

### 5. **Reading Characters**
   - **Purpose**: Reads a single character or handles input one character at a time.
   - **Example**:
     ```c
     char ch;
     printf("Enter a character: ");
     scanf(" %c", &ch); // Note the space before %c to ignore leading whitespace
     ```

---

### A simple program on taking two numbers as input and get the sum as output...

```c
#include <stdio.h>

int main() 
{
    int num1;
    int num2;

// Prompt user for input
    printf("Enter a number: ");
    scanf("%d", &num1);
  
    printf("Enter another number: ");
    scanf("%d", &num2);

// Display the result
    printf("The sum of %d and %d is %d \n", num1, num2, num1 + num2);
    return 0;

}

```


**This can also be done by taking another variable for calculating the sum...we can choose whatever approach we like**