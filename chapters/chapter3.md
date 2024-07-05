### Chapter 3: Core Concepts

#### 3.1 Data Types and Variables

In C, data types must be explicitly declared, and each variable must have a defined type. This contrasts with Python, where variables are dynamically typed and can change type during execution.

##### Common Data Types in C
- `int`: Integer type
- `float`: Single-precision floating-point type
- `double`: Double-precision floating-point type
- `char`: Single character type
- `void`: Represents the absence of type

**Python:**
```python
x = 10          # Integer
y = 20.5        # Float
name = "Alice"  # String
```

**C:**
```c
#include <stdio.h>

int main() {
    int x = 10;           // Integer
    float y = 20.5;       // Float
    double z = 30.15;     // Double
    char ch = 'A';        // Character

    printf("Integer: %d\n", x);
    printf("Float: %.2f\n", y);
    printf("Double: %.2lf\n", z);
    printf("Character: %c\n", ch);

    return 0;
}
```

**Explanation:**
- In Python, variables are created by simply assigning a value. The type is inferred at runtime.
- In C, variables must be declared with a specific type before use. The type is fixed at compile time.

#### 3.2 Operators and Expressions

C provides a rich set of operators to perform various operations on variables, similar to Python. However, there are differences in how some operators behave.

##### 3.2.1 Arithmetic Operators
- `+`: Addition
- `-`: Subtraction
- `*`: Multiplication
- `/`: Division
- `%`: Modulus (remainder)

**Python:**
```python
a = 10
b = 3
print(a + b)  # 13
print(a - b)  # 7
print(a * b)  # 30
print(a / b)  # 3.3333333333333335
print(a % b)  # 1
```

**C:**
```c
#include <stdio.h>

int main() {
    int a = 10, b = 3;
    printf("a + b = %d\n", a + b);
    printf("a - b = %d\n", a - b);
    printf("a * b = %d\n", a * b);
    printf("a / b = %d\n", a / b);  // Integer division
    printf("a %% b = %d\n", a % b); // Modulus

    return 0;
}
```

**Explanation:**
- In Python, `/` performs floating-point division by default.
- In C, `/` performs integer division if both operands are integers. To perform floating-point division, at least one operand must be a float or double.

##### 3.2.2 Comparison Operators
- `==`: Equal to
- `!=`: Not equal to
- `>`: Greater than
- `<`: Less than
- `>=`: Greater than or equal to
- `<=`: Less than or equal to

**Python:**
```python
a = 5
b = 10
print(a == b)  # False
print(a != b)  # True
print(a > b)   # False
print(a < b)   # True
print(a >= b)  # False
print(a <= b)  # True
```

**C:**
```c
#include <stdio.h>

int main() {
    int a = 5, b = 10;
    printf("a == b: %d\n", a == b);
    printf("a != b: %d\n", a != b);
    printf("a > b: %d\n", a > b);
    printf("a < b: %d\n", a < b);
    printf("a >= b: %d\n", a >= b);
    printf("a <= b: %d\n", a <= b);

    return 0;
}
```

**Explanation:**
- Both Python and C use similar comparison operators, but in C, the result of a comparison is 0 (false) or 1 (true), which can be used directly in arithmetic expressions.

##### 3.2.3 Logical Operators
- `&&`: Logical AND
- `||`: Logical OR
- `!`: Logical NOT

**Python:**
```python
a = True
b = False
print(a and b)  # False
print(a or b)   # True
print(not a)    # False
```

**C:**
```c
#include <stdio.h>

int main() {
    int a = 1, b = 0; // In C, 1 is true and 0 is false
    printf("a && b: %d\n", a && b);
    printf("a || b: %d\n", a || b);
    printf("!a: %d\n", !a);

    return 0;
}
```

**Explanation:**
- In Python, `and`, `or`, and `not` are logical operators.
- In C, logical operators are `&&`, `||`, and `!`.

#### 3.3 Control Structures

Control structures allow you to control the flow of execution in your programs. Python and C share similar control structures, but with different syntax.

##### 3.3.1 Conditionals
- `if`
- `else if` (`elif` in Python)
- `else`

**Python:**
```python
x = 10

if x > 0:
    print("Positive")
elif x == 0:
    print("Zero")
else:
    print("Negative")
```

**C:**
```c
#include <stdio.h>

int main() {
    int x = 10;

    if (x > 0) {
        printf("Positive\n");
    } else if (x == 0) {
        printf("Zero\n");
    } else {
        printf("Negative\n");
    }

    return 0;
}
```

**Explanation:**
- In Python, `elif` is used for additional conditions.
- In C, `else if` is used.

##### 3.3.2 Loops
- `for`
- `while`
- `do-while` (only in C)

**Python:**
```python
# For loop
for i in range(5):
    print(i)

# While loop
i = 0
while i < 5:
    print(i)
    i += 1
```

**C:**
```c
#include <stdio.h>

int main() {
    // For loop
    for (int i = 0; i < 5; i++) {
        printf("i = %d\n", i);
    }

    // While loop
    int i = 0;
    while (i < 5) {
        printf("i = %d\n", i);
        i++;
    }

    // Do-while loop
    i = 0;
    do {
        printf("i = %d\n", i);
        i++;
    } while (i < 5);

    return 0;
}
```

**Explanation:**
- Python’s `for` loop is designed to iterate over sequences, while C’s `for` loop is more general and requires explicit initialization, condition, and increment statements.
- C has a `do-while` loop that guarantees the loop body executes at least once.

#### 3.4 Functions


##### 3.4.1 Function Definition
Functions are reusable blocks of code that perform a specific task. Both Python and C use functions, but with different syntax and some variations in usage.

**Python:**
```python
def add(a, b):
    return a + b

result = add(3, 4)
print("Sum:", result)
```

**C:**
```c
#include <stdio.h>

// Function declaration
int add(int a, int b);

int main() {
    int result = add(3, 4);
    printf("Sum: %d\n", result);
    return 0;
}

// Function definition
int add(int a, int b) {
    return a + b;
}
```

**Explanation:**
- In Python, functions are defined with the `def` keyword and do not require explicit type declarations for parameters or return values.
- In C, functions must be declared before use (either via a prototype or definition), and the types of parameters and return values must be specified.

##### 3.4.2 Function Prototypes
Function prototypes are declarations of functions that specify their return types and parameters. They are usually placed at the beginning of the file, before the `main` function.

**Python:** Function definitions can appear in any order as long as they are called after their definition.

**C:**
```c
#include <stdio.h>

// Function prototypes
void greet();
int multiply(int a, int b);

int main() {
    greet();
    int result = multiply(3, 4);
    printf("Product: %d\n", result);
    return 0;
}

void greet() {
    printf("Hello, World!\n");
}

int multiply(int a, int b) {
    return a * b;
}
```

##### 3.4.3 Scope and Lifetime of Variables
Variables in C have different scopes and lifetimes based on where they are declared.

**Python:**
```python
global_var = 10  # Global variable

def print_global():
    print("Global variable:", global_var)

def main():
    local_var = 20  # Local variable
    print("Local variable:", local_var)
    print_global()

main()

Local variable: 20
Global variable: 10

```

**C:**
```c
#include <stdio.h>

// Global variable
int globalVar = 10;

void printGlobalVar() {
    printf("Global variable: %d\n", globalVar);
}

int main() {
    // Local variable
    int localVar = 20;
    printf("Local variable: %d\n", localVar);

    printGlobalVar();
    return 0;
}

Local variable: 20
Global variable: 10

```

**Explanation:**
- In Python, variables defined outside any function are global, and those defined inside a function are local.
- In C, the same rules apply, but the lifetime of local variables is limited to the block in which they are defined.

