### Chapter 7: Practical Applications

This chapter provides practical examples to help you apply your C programming knowledge. By building real-world applications, you'll gain a deeper understanding of how to use C effectively. We will cover three projects: writing a simple game, building a small web server, and creating system utilities.

#### 7.1 Writing a Simple Game: Guess the Number

Let's create a simple number guessing game. The program will generate a random number, and the user will have to guess it.

**Python:**
```python
import random

def guess_the_number():
    number = random.randint(1, 100)
    guess = None

    while guess != number:
        guess = int(input("Guess the number between 1 and 100: "))
        if guess < number:
            print("Too low!")
        elif guess > number:
            print("Too high!")
        else:
            print("Congratulations! You guessed the number.")

guess_the_number()
```

**C:**
```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
    int number, guess;

    // Initialize random number generator
    srand(time(0));
    number = rand() % 100 + 1;

    printf("Guess the number between 1 and 100: ");

    do {
        scanf("%d", &guess);
        if (guess < number) {
            printf("Too low! Try again: ");
        } else if (guess > number) {
            printf("Too high! Try again: ");
        } else {
            printf("Congratulations! You guessed the number.\n");
        }
    } while (guess != number);

    return 0;
}
```

**Explanation:**
- The program uses the `rand()` function to generate a random number between 1 and 100.
- The `srand(time(0))` initializes the random number generator with the current time.
- A `do-while` loop is used to prompt the user for guesses until they guess the correct number.

#### 7.2 Building a Small Web Server

We'll build a simple web server that serves static HTML pages. For simplicity, we'll use a basic socket programming approach.

**Python:**
```python
import socket

def start_server():
    server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    server_socket.bind(('localhost', 8080))
    server_socket.listen(1)
    print("Server is running on port 8080...")

    while True:
        client_socket, client_address = server_socket.accept()
        request = client_socket.recv(1024).decode()
        print("Request received:")
        print(request)

        response = 'HTTP/1.0 200 OK\n\nHello, World!'
        client_socket.sendall(response.encode())
        client_socket.close()

start_server()
```

**C:**
```c
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include <unistd.h>
#include <arpa/inet.h>

int main() {
    int server_fd, new_socket;
    struct sockaddr_in address;
    int addrlen = sizeof(address);
    char buffer[1024] = {0};
    char *hello = "HTTP/1.0 200 OK\n\nHello, World!";

    // Creating socket file descriptor
    if ((server_fd = socket(AF_INET, SOCK_STREAM, 0)) == 0) {
        perror("socket failed");
        exit(EXIT_FAILURE);
    }

    // Bind the socket to the port 8080
    address.sin_family = AF_INET;
    address.sin_addr.s_addr = INADDR_ANY;
    address.sin_port = htons(8080);

    if (bind(server_fd, (struct sockaddr *)&address, sizeof(address)) < 0) {
        perror("bind failed");
        exit(EXIT_FAILURE);
    }

    if (listen(server_fd, 3) < 0) {
        perror("listen");
        exit(EXIT_FAILURE);
    }

    printf("Server is running on port 8080...\n");

    // Accept incoming connection
    while (1) {
        if ((new_socket = accept(server_fd, (struct sockaddr *)&address, (socklen_t *)&addrlen)) < 0) {
            perror("accept");
            exit(EXIT_FAILURE);
        }

        read(new_socket, buffer, 1024);
        printf("Request received:\n%s\n", buffer);
        write(new_socket, hello, strlen(hello));
        close(new_socket);
    }

    return 0;
}
```

**Explanation:**
- The server listens on port 8080 for incoming HTTP requests.
- Upon receiving a request, it sends a simple "Hello, World!" response.
- The server uses basic socket programming functions like `socket()`, `bind()`, `listen()`, `accept()`, and `write()`.

#### 7.3 Creating System Utilities: File Copy Utility

We'll create a utility to copy the contents of one file to another.

**Python:**
```python
def copy_file(src, dst):
    with open(src, 'r') as f_src:
        with open(dst, 'w') as f_dst:
            f_dst.write(f_src.read())

copy_file('source.txt', 'destination.txt')
```

**C:**
```c
#include <stdio.h>
#include <stdlib.h>

void copyFile(const char *src, const char *dst) {
    FILE *f_src = fopen(src, "r");
    if (f_src == NULL) {
        perror("Error opening source file");
        exit(EXIT_FAILURE);
    }

    FILE *f_dst = fopen(dst, "w");
    if (f_dst == NULL) {
        perror("Error opening destination file");
        fclose(f_src);
        exit(EXIT_FAILURE);
    }

    char ch;
    while ((ch = fgetc(f_src)) != EOF) {
        fputc(ch, f_dst);
    }

    fclose(f_src);
    fclose(f_dst);
}

int main() {
    copyFile("source.txt", "destination.txt");
    printf("File copied successfully.\n");
    return 0;
}
```

**Explanation:**
- The program opens the source file for reading and the destination file for writing.
- It reads the contents of the source file character by character and writes them to the destination file.
- Proper error handling ensures the program handles file opening errors gracefully.
