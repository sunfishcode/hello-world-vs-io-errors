# Fixed Hello World examples

As mentioned in the [README.md](README.md), many languages do have a way
to explicitly test for errors on stdout. This file collects examples of
how to do this in various languages.

## C

```c
#include <stdio.h>
#include <stdlib.h>

int main(void) {
    printf("Hello, World!\n");

    if (fflush(stdout) != 0 || ferror(stdout) != 0) {
        return EXIT_FAILURE;
    }

    return EXIT_SUCCESS;
}
```
