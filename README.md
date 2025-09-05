# clang-barrc

A `.clang-format` file to adhere to the [Barr Group's Embedded C Coding Standards](standards).

The base of this `.clang-format` file originates from [petertorelli's](https://github.com/petertorelli/clang-format-barr-c) format file.

## Fixes from `petertorelli`'s file:
- Adds proper spacing between `*` and a parameter (3.1.e)
- Removes the return type on a new line
    - Although the Barr-C standard displays all examples of code using this style, it is *not* a requirement anywhere.

## Requirements
- `clang-format` >= 19.0

## Installation

Download the `.clang-format` file and place it in your home directory. `clang-format` will find this automatically unless a project-level format file has been given.

## Comparison

### New file
```c
#include <stdbool.h>
#include <stdio.h>

bool print_me (char * p_buf)
{
    bool b_status = false;

    if (NULL == p_buf)
    {
        goto EXIT;
    }

    printf("Hello, %s\n", p_buf);
    b_status = true;

EXIT:
    return (b_status);
}

int main (void)
{
    printf("Hello world!\n");
}

```

### Peter Torelli's
```c
#include <stdbool.h>
#include <stdio.h>

bool
print_me (char *p_buf)
{
    bool b_status = false;

    if (NULL == p_buf)
    {
        goto EXIT;
    }

    printf("Hello, %s\n", p_buf);
    b_status = true;

EXIT:
    return (b_status);
}

int
main (void)
{
    printf("Hello world!\n");
}
```

