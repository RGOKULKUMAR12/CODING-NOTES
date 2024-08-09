>***Program to find factorial of the number***

| S NO | INPUT | OUTPUT  |
| :--: | :---: | :-----: |
|  1   |   5   |   120   |
|  2   |  10   | 3628800 |
```c
#include <stdio.h>

int fact(int n) {
    if (n == 0 || n == 1)
        return 1;
    return n * fact(n - 1);
}

int main() {
    long int n;
    scanf("%ld", &n);
    
    // Check if the input is non-negative
    if (n < 0) {
        printf("Invalid input: factorial is not defined for negative  numbers.\n");
        return 1;
    }
    
    // Calculate factorial
    int x = fact(n);
    printf("%d", x);
    
    return 0;
}

```
---