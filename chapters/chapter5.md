### Chapter 5: C Libraries

Libraries in C are collections of precompiled functions and definitions that you can use to enhance the functionality of your programs. Understanding how to use these libraries and how to create your own is crucial for efficient C programming.

#### 5.1 Standard Library Functions

The C Standard Library provides a wealth of functions for performing input/output operations, string manipulations, mathematical computations, and more. Here are some commonly used standard library functions.

##### 5.1.1 String Handling

String handling functions in C are found in the `<string.h>` library.

**Common Functions:**
- `strlen`: Returns the length of a string.
- `strcpy`: Copies one string to another.
- `strcat`: Concatenates two strings.
- `strcmp`: Compares two strings.

**Example:**
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str1[20] = "Hello";
    char str2[20] = "World";
    char str3[20];

    // Copy str1 to str3
    strcpy(str3, str1);
    printf("strcpy: %s\n", str3);

    // Concatenate str1 and str2
    strcat(str1, str2);
    printf("strcat: %s\n", str1);

    // Length of str1
    printf("strlen: %lu\n", strlen(str1));

    // Compare str1 and str2
    int cmp = strcmp(str1, str2);
    printf("strcmp: %d\n", cmp);

    return 0;
}
```

##### 5.1.2 Mathematical Functions

Mathematical functions are available in the `<math.h>` library.

**Common Functions:**
- `sqrt`: Computes the square root.
- `pow`: Raises a number to a power.
- `sin`, `cos`, `tan`: Trigonometric functions.
- `fabs`: Computes the absolute value of a floating-point number.

**Example:**
```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = 16.0;

    printf("Square root of %.2f: %.2f\n", num, sqrt(num));
    printf("2 raised to the power 3: %.2f\n", pow(2, 3));
    printf("Sine of 45 degrees: %.2f\n", sin(45 * M_PI / 180)); // Convert degrees to radians

    return 0;
}
```

##### 5.1.3 Time and Date Functions

Time and date functions are found in the `<time.h>` library.

**Common Functions:**
- `time`: Returns the current time.
- `ctime`: Converts time to a string.
- `difftime`: Computes the difference between two times.
- `strftime`: Formats date and time.

**Example:**
```c
#include <stdio.h>
#include <time.h>

int main() {
    time_t current_time;
    time(&current_time);

    printf("Current time: %s", ctime(&current_time));

    return 0;
}
```

#### 5.2 Writing and Using Header Files

Header files in C are used to declare functions and variables that can be shared across multiple source files. They typically have a `.h` extension.

**Creating a Header File:**
1. Create a file named `myheader.h`.
2. Declare functions and variables in the header file.

**myheader.h:**
```c
// Function prototype
void greet();
```

**Using the Header File:**
1. Include the header file in your source file using `#include`.

**main.c:**
```c
#include <stdio.h>
#include "myheader.h"

// Function definition
void greet() {
    printf("Hello from the header file!\n");
}

int main() {
    greet();
    return 0;
}
```

**Explanation:**
- `#include "myheader.h"` includes the header file.
- The `greet` function is declared in the header file and defined in the source file.

#### 5.3 Linkers and Makefiles

Linkers and makefiles are essential tools for managing larger C projects. The linker combines multiple object files into a single executable, while a makefile automates the build process.

##### 5.3.1 Using the Linker

When compiling multiple source files, you can use the linker to combine them into a single executable.

**Example:**
1. Create two source files `file1.c` and `file2.c`.

**file1.c:**
```c
#include <stdio.h>

void function1() {
    printf("This is function1 from file1.\n");
}
```

**file2.c:**
```c
void function1();

int main() {
    function1();
    return 0;
}
```

2. Compile and link the files:
```bash
gcc -c file1.c
gcc -c file2.c
gcc file1.o file2.o -o myprogram
./myprogram
```

**Explanation:**
- `gcc -c file1.c` compiles `file1.c` into an object file `file1.o`.
- `gcc -c file2.c` compiles `file2.c` into an object file `file2.o`.
- `gcc file1.o file2.o -o myprogram` links the object files into an executable `myprogram`.

##### 5.3.2 Writing a Makefile

A makefile automates the build process by specifying how to compile and link the program.

**Example Makefile:**
```Makefile
# Makefile for building myprogram

# Compiler
CC = gcc

# Compiler flags
CFLAGS = -Wall

# Target executable
TARGET = myprogram

# Source files
SRCS = file1.c file2.c

# Object files
OBJS = $(SRCS:.c=.o)

# Build the target
$(TARGET): $(OBJS)
    $(CC) $(CFLAGS) -o $(TARGET) $(OBJS)

# Compile source files into object files
%.o: %.c
    $(CC) $(CFLAGS) -c $< -o $@

# Clean up object files and executable
clean:
    rm -f $(OBJS) $(TARGET)
```

**Explanation:**
- `CC = gcc` sets the compiler to `gcc`.
- `CFLAGS = -Wall` enables all compiler warnings.
- `TARGET = myprogram` sets the name of the executable.
- `SRCS = file1.c file2.c` lists the source files.
- `OBJS = $(SRCS:.c=.o)` converts source file names to object file names.
- `$(TARGET): $(OBJS)` defines the target and its dependencies.
- `$(CC) $(CFLAGS) -o $(TARGET) $(OBJS)` links the object files to create the executable.
- `%.o: %.c` compiles each source file into an object file.
- `clean:` removes the object files and executable.

**Building with Make:**
```bash
make
./myprogram
make clean
```

**Explanation:**
- `make` compiles and links the program.
- `./myprogram` runs the executable.
- `make clean` removes the object files and executable.

---

This chapter covers the use of standard library functions, creating and using header files, and managing builds with linkers and makefiles. These tools are essential for efficient C programming and managing larger projects.