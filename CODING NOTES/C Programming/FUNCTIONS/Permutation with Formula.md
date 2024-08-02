> ***Given two integers `n1` and `n2`, write a program to calculate the number of permutations of `n1` items taken `n2` at a time. The formula for permutations is given by: $P(n1,n2)=\frac{n1!}{(n1 - n2)!}​$ where `!` denotes factorial.***
>

| S N0 | INPUT            | OUTPUT |     |
| ---- | ---------------- | :----: | --- |
| 01   | n1 = 5<br>n2 = 3 |   60   |     |
| 02   | n1 = 5<br>n2 = 6 |  120   |     |
```c
#include <stdio.h>

int fact(int n1) {
    if (n1 <= 1)
        return 1;
    return n1 * fact(n1 - 1);
}

int per(int n1, int n2) {
    return fact(n1) / fact(n1 - n2);
}

int main() {
    int num1, num2;
    scanf("%d %d", &num1, &num2);
    
    int result = per(num1, num2);
    printf("%d", result);
    return 0;
}
```
---