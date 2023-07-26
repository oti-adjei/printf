Hey there! Welcome to our project where we've been given the challenge of recreating the famous `printf` function in C. 

## Introduction

As we all know, the `printf` function in C is super powerful, allowing us to print various data types with specified formatting options. The purpose of this assignment was to deepen your understanding of string formatting and handling variable arguments in C. Our custom printf function will be referred to as `_printf` to distinguish it from the standard library's `printf`.

## Project Structure

For this project, we've organized our code into several files, each serving a specific purpose:

1. `main.c`: This is where all the magic happens! We'll test our custom `_printf` function by calling it with various format strings and arguments.

2. `main.h`: In this header file, we've included function prototypes and any necessary macros or typedefs for the project.

3. `custom_handle_print.c`: This file contains the core logic for handling the format specifiers and printing accordingly.

4. `custom_writehandlers.c`: Here, we have implemented functions to write characters to the output stream.

5. `7-get_flags.c`: In this file, we take care of extracting any flags specified in the format string.

6. `8-get_size.c`: Here, we determine the size of the output string to be printed.

7. `9-get_width.c`: This file is responsible for handling width formatting.

8. `100-get_precision.c`: Similarly, this one deals with precision formatting.

9. `101-string_utils.c`: This file holds utility functions used throughout the project.

And of course, we have additional files for each format specifier, where we handle the actual logic for printing each specific data type.

## Function Description

Our custom `_printf` function is declared as follows:

```c
int _printf(const char *format, ...);
```

It's designed to take a format string as the first argument, followed by a variable number of arguments corresponding to the format specifiers in the format string. The function returns the number of characters printed (excluding the null terminator) or a negative value if an error occurs.

## Supported Format Specifiers

To make our custom `_printf` function versatile as required, we've added support for some format specifiers:

- `%s`: For printing strings.
- `%c`: To print a single character.
- `%d` and `%i`: For printing integers (signed decimal).
- `%u`: To print unsigned integers (unsigned decimal).
- `%o`: To print unsigned integers in octal format.
- `%x` and `%X`: For printing unsigned integers in lowercase and uppercase hexadecimal format, respectively.
- `%p`: To print pointer addresses in hexadecimal format.
- `%%`: To print a single percent sign.

## How to Use

Using our custom `_printf` function is quite straight forward! Just include the `main.h` header file in your C source file(`main.c`).Then, you can call `_printf` with a format string and any necessary arguments. The format string specifies how the subsequent arguments should be formatted and printed.

## Example

Let's showcase an example of our custom `_printf` function with the `main.c` file given to us:

```c
#include <stdio.h>
#include "main.h"

int main(void)
{
    /**
    * main - Entry point
    *
    * Return: Always 0
    */
    int len;
    unsigned int ui;
    void *addr;

    // Testing _printf function
    len = _printf("Let's try to printf a simple sentence.\n");
    ui = (unsigned int)INT_MAX + 1024;
    addr = (void *)0x7ffe637541f0;
    _printf("Length:[%d, %i]\n", len, len);
    _printf("Negative:[%d]\n", -762534);
    _printf("Unsigned:[%u]\n", ui);
    _printf("Unsigned octal:[%o]\n", ui);
    _printf("Unsigned hexadecimal:[%x, %X]\n", ui, ui);
    _printf("Character:[%c]\n", 'H');
    _printf("String:[%s]\n", "I am a string !");
    _printf("Address:[%p]\n", addr);
    len = _printf("Percent:[%%]\n");
    _printf("Len:[%d]\n", len);
    _printf("Unknown:[%r]\n");

    return (0);
}
```

To run it just make your main.c file an exutable (`chmodu+x main.c`) and then compile it with the following: '**gcc -Wall -Wextra -Werror -pedantic -std=gnu89 -Wno-format *.c**' . (You can research on the tags but in summary they allow for efficient and as close to error free compiled code.)

## Limitations & Problem-Solving

Before we wrap up, we want to mention that our custom `_printf` function may not support all the features and edge cases of the standard `printf` function. For this assignment, we're mainly focusing on a basic implementation.
Developing our custom `printf` function has been an enriching experience that strengthened our problem-solving and critical thinking skills. Here's how:

    1. **Project Structure:** Organizing the code into separate files allowed us to tackle the problem systematically, breaking it down into manageable components for easier implementation and maintenance.
    
    2. **Handling Format Specifiers:** Dealing with various format specifiers required analyzing different data types and designing efficient solutions tailored to each case.
    
    3. **Debugging and Testing:** We honed our debugging skills by identifying and fixing bugs encountered during implementation, while comprehensive testing ensured the correctness of our function.
    
    4. **Edge Cases:** Handling edge cases like invalid format specifiers and special characters demanded careful consideration and thoughtful solutions.
    
    5. **Pointers and Memory Management:** Working with pointers and managing memory deepened our understanding of C programming.
    
    6. **Collaboration and Communication:** Collaborating on the project fostered effective communication and teamwork, enabling us to support each other's progress.
    
    In conclusion, this project has been a valuable learning experience, empowering us with practical skills and knowledge to tackle future programming challenges with confidence.

## Conclusion

And that's it! We hope you'll enjoy exploring our custom `_printf` function and get a deeper understanding of the mechanics behind the standard `printf` function. By breaking the project into multiple files and handling each format specifier separately, we've made our implementation clean and modular.

Happy coding and do hard things 😄
