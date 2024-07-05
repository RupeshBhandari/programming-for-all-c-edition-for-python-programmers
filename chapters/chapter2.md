### Chapter 2: Building a Simple Program

#### 2.1 Compilers vs. Interpreters
One major difference between C and Python is how they execute programs. Python is an interpreted language, meaning code is executed line by line. C is a compiled language, where the code is first translated into machine code by a compiler, and then the machine code is executed.

##### Example:
**Python:**
```python
print("Hello, World!")
```
To execute:
```bash
python my_program.py
```

**C:**
```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```
To compile and execute:
```bash
gcc my_program.c -o my_program
./my_program
```

#### 2.2 Writing and Compiling Your First C Program
Here is a simple C program that prints "Hello, World!".

**Code:**
```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```

**Steps to Compile and Run:**
1. Save the code in a file named `hello.c`.
2. Open a terminal and navigate to the directory containing `hello.c`.
3. Compile the program using GCC (GNU Compiler Collection):
   ```bash
   gcc hello.c -o hello
   ```
4. Run the compiled program:
   ```bash
   ./hello
   ```

**Explanation:**
- `#include <stdio.h>`: This line includes the standard input-output library, necessary for using the `printf` function.
- `int main() { ... }`: This is the main function where the program execution starts.
- `printf("Hello, World!\n");`: This line prints "Hello, World!" followed by a newline character.
- `return 0;`: This line indicates that the program ended successfully.

#### 2.3 Variable Declarations
In C, you must declare the type of each variable before you use it. This is different from Python, where variables are dynamically typed.

**Python:**
```python
x = 10
```

**C:**
```c
int x = 10;
```

Variables in C must be declared at the beginning of a block, typically at the top of a function.

**Example:**
```c
#include <stdio.h>

int main() {
    int x = 10;
    printf("x is %d\n", x);
    return 0;
}
```

**Explanation:**
- `int x = 10;`: This declares an integer variable `x` and initializes it with the value 10.
- `%d`: This format specifier is used to print an integer value.

#### 2.4 Whitespace and Formatting
Whitespace is not significant in C as it is in Python. Statements are terminated with semicolons, and blocks of code are enclosed in braces `{}`.

**Python:**
```python
if x > 0:
    print("Positive")
else:
    print("Non-positive")
```

**C:**
```c
#include <stdio.h>

int main() {
    int x = 10;

    if (x > 0) {
        printf("Positive\n");
    } else {
        printf("Non-positive\n");
    }
    return 0;
}
```

**Explanation:**
- The `if` statement in C requires parentheses around the condition and braces `{}` to define the block of code to be executed if the condition is true or false.

#### 2.5 Basic Input and Output with `printf`
The `printf` function is used for output in C. It allows formatted output, similar to Python's `print`.

**Python:**
```python
name = "Alice"
print(f"Hello, {name}!")
```

**C:**
```c
#include <stdio.h>

int main() {
    char name[] = "Alice";
    printf("Hello, %s!\n", name);
    return 0;
}
```

**Explanation:**
- `char name[] = "Alice";`: This declares a character array (string) `name` and initializes it with "Alice".
- `%s`: This format specifier is used to print a string.
- `\n`: This represents a newline character.

**More Examples with `printf`:**

**Example 1: Printing integers and floats**
```c
#include <stdio.h>

int main() {
    int a = 5;
    float b = 4.5;

    printf("Integer: %d\n", a);
    printf("Float: %.2f\n", b);

    return 0;
}
```
**Explanation:**
- `%d`: Prints an integer.
- `%.2f`: Prints a floating-point number with two decimal places.

**Example 2: Printing multiple variables**
```c
#include <stdio.h>

int main() {
    int num_sol = 2;
    float sol0 = 4.0;
    float sol1 = 1.0;

    printf("# solns: %d, solns: %.1f, %.1f\n", num_sol, sol0, sol1);

    return 0;
}
```
**Explanation:**
- `printf` can handle multiple variables by listing them after the format string.
