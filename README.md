# _printf - Custom printf Function in C

## Description

`_printf` is a custom implementation of the standard C library function `printf`. This project replicates the behavior of `printf`, supporting multiple format specifiers and handling variadic arguments using only **authorized low-level functions** — no use of `printf`, `puts`, or `sprintf`.

It was developed as part of a systems programming curriculum, focused on gaining deep understanding of how formatted output works under the hood using `write` and variadic macros.

---

## ✅ Supported Format Specifiers

The `_printf` function currently supports the following formats:

| Format | Description                            |
|--------|----------------------------------------|
| `%c`   | Prints a single character              |
| `%s`   | Prints a string of characters          |
| `%d`   | Prints a signed decimal integer        |
| `%i`   | Alias for `%d`                         |
| `%u`   | Prints an unsigned decimal integer     |
| `%o`   | Prints an unsigned octal number        |
| `%x`   | Prints an unsigned hexadecimal number (lowercase) |
| `%X`   | Prints an unsigned hexadecimal number (uppercase) |
| `%p`   | Prints a memory address (pointer)      |
| `%%`   | Prints a literal percent sign          |
| `%r`   | (Extension) Prints a reversed string   |

⚠️ If the format specifier is not recognized, it will be printed as is: `%<char>`.

---

## ⚙️ Compilation

To compile the project, use the following command:

```bash
gcc -Wall -Werror -Wextra -pedantic -std=gnu89 -Wno-format *.c

⚠️ Important: Do not include any .c files with main() in the root directory. Keep test files inside a /tests folder.

📁 Project Structure

printf/
├── main.h           # Main header file with prototypes and macros
├── _printf.c        # Core implementation of _printf
├── handle_format.c  # Format specifier handling logic
├── utils.c          # Helper functions (e.g., string, number handling)
├── README.md        # This file
├── tests/
│   └── main.c       # Test files to compare _printf vs printf

🧪 Usage Example

#include "main.h"

int main(void)
{
    int len = _printf("Hello %s, your score is %d%%!\n", "Ivan", 95);
    _printf("Printed %d characters\n", len);
    return (0);
}

🛠️ Allowed Functions
Only the following functions and macros are allowed in this project:

- write (man 2 write)

- malloc, free (man 3 malloc / free)

- va_start, va_end, va_arg, va_copy (man 3 stdarg)

No other standard I/O or string formatting functions are permitted.

📦 Testing
To test and compare the behavior of _printf against the standard printf, you can use:

cd tests
gcc -Wall -Werror -Wextra -pedantic -std=gnu89 -Wno-format ../*.c *.c -o printf_test
./printf_test

🤝 Authors
Project developed by:

- Ivan Barbosa Gomez
- Alexander Zuleta

📜 License
This project is developed for educational purposes to explore low-level C programming and software architecture. You are welcome to reuse or modify it with proper credit.