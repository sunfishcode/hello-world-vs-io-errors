# Fixed Hello World examples

As mentioned in the [README.md](README.md), many languages do have a way
to explicitly test for errors on stdout. This file collects examples of
how to do this in various languages.

## C

```C
#include <stdio.h>
#include <stdlib.h>

int main(void)
{
        // stdout buffer setting, Python way
        // setvbuf(stdout, (char *)NULL, _IONBF, BUFSIZ);
        // OR
        // stdout buffer setting, Perl way
        setvbuf(stdout, NULL, _IOLBF, 0);

        printf("Hello, World!\n");
        if (ferror(stdout) || feof(stdout)) {
                perror("ERROR: printing failed");
                return EXIT_FAILURE;
        }

        return fflush(stdout);
}
```

## C++

```C++
#include <iostream>
#include <cstdlib>
using namespace std;

int main(void)
{
        if (!(cout << "Hello, World!" << endl)) {
                perror("ERROR: printing failed");
                return EXIT_FAILURE;
        }
        return EXIT_SUCCESS;
}
```
