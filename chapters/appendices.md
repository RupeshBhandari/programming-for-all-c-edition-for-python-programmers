### Appendices

This section provides additional resources, reference sheets, further reading, and a glossary of terms to aid in your understanding and application of C programming concepts.

#### Appendix A: Reference Sheets

##### A.1 Common C Functions

**Standard Input/Output (`stdio.h`):**
- `printf`: Prints formatted output to the standard output.
- `scanf`: Reads formatted input from the standard input.
- `fprintf`: Prints formatted output to a file.
- `fscanf`: Reads formatted input from a file.
- `fopen`: Opens a file.
- `fclose`: Closes a file.
- `fgets`: Reads a string from a file.
- `fputs`: Writes a string to a file.

**String Handling (`string.h`):**
- `strlen`: Returns the length of a string.
- `strcpy`: Copies a string.
- `strncpy`: Copies a specified number of characters from a string.
- `strcat`: Concatenates two strings.
- `strncat`: Concatenates a specified number of characters from a string.
- `strcmp`: Compares two strings.
- `strncmp`: Compares a specified number of characters from two strings.

**Memory Management (`stdlib.h`):**
- `malloc`: Allocates memory.
- `calloc`: Allocates memory and initializes it to zero.
- `realloc`: Reallocates memory.
- `free`: Frees allocated memory.

**Mathematical Functions (`math.h`):**
- `sqrt`: Computes the square root.
- `pow`: Raises a number to a power.
- `sin`, `cos`, `tan`: Trigonometric functions.
- `fabs`: Computes the absolute value of a floating-point number.

##### A.2 C Syntax Cheat Sheet

**Variable Declarations:**
```c
int x;
float y;
char z;
```

**Control Structures:**
```c
// If-Else
if (condition) {
    // code
} else if (condition) {
    // code
} else {
    // code
}

// For Loop
for (initialization; condition; increment) {
    // code
}

// While Loop
while (condition) {
    // code
}

// Do-While Loop
do {
    // code
} while (condition);
```

**Functions:**
```c
return_type function_name(parameters) {
    // code
    return value;
}
```

**Pointers:**
```c
int *ptr;
ptr = &variable;
value = *ptr;
```

#### Appendix B: Further Reading and Resources

To deepen your understanding of C programming and explore advanced topics, consider the following resources:

**Books:**
- "The C Programming Language" by Brian W. Kernighan and Dennis M. Ritchie
- "C Programming: A Modern Approach" by K.N. King
- "C Primer Plus" by Stephen Prata

**Online Courses:**
- [Harvard's CS50: Introduction to Computer Science](https://www.edx.org/course/cs50s-introduction-to-computer-science)
- [Coursera's C for Everyone: Programming Fundamentals](https://www.coursera.org/learn/c-for-everyone)

**Websites:**
- [GeeksforGeeks C Programming](https://www.geeksforgeeks.org/c-programming-language/)
- [Tutorialspoint C Programming](https://www.tutorialspoint.com/cprogramming/index.htm)

#### Appendix C: Glossary of Terms

- **Array:** A collection of elements of the same type stored in contiguous memory locations.
- **Buffer Overflow:** A condition where data exceeds the buffer's storage capacity, leading to adjacent memory being overwritten.
- **Compiler:** A program that translates source code into machine code.
- **Dangling Pointer:** A pointer that points to a memory location that has been freed.
- **Dynamic Memory Allocation:** The process of allocating memory storage during runtime using functions like `malloc`, `calloc`, and `realloc`.
- **Function Prototype:** A declaration of a function that specifies the function's name, return type, and parameters.
- **Library:** A collection of precompiled functions and definitions used to enhance program functionality.
- **Pointer:** A variable that stores the memory address of another variable.
- **Struct:** A user-defined data type in C that groups related variables of different types.
- **Variable:** A named storage location in memory that holds a value.