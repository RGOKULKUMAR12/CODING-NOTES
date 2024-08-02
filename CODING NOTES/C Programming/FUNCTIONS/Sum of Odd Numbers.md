>***Given two integers `n1` and `n2`, write a program to calculate the sum of all odd numbers between `n1` and `n2` (inclusive).***

| S NO |   INPUT    | OUPUT  |
| :--: | :--------: | :----: |
|  1   | 3<br>9<br> | 24<br> |
|  2   |  11<br>13  |   11   |
```c
#include <stdio.h>
#include <string.h>

// Sum of Odd Numbers Program

int odd(int n, int n2) {
    if (n <= n2) {
        return n + odd(n + 2, n2);
    }
    return 0;
}

int main() {
    int n1, n2;
    
    scanf("%d", &n1);
    scanf("%d", &n2);
    
    int max;
    if (n1 % 2 == 0)
        max = odd(n1 + 1, n2);
    else
        max = odd(n1, n2);
    
    printf("%d", max);
    
    return 0;
}

```
---