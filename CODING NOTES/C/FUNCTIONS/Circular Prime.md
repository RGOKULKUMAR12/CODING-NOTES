>***Write a program to determine if a given number is a circular prime. A circular prime is a prime number that remains prime under any rotation of its digits. For instance, 197 is a circular prime because 197, 971, and 719 are all prime numbers.***

>[!Tip]
>- Check how to find : [[Prime Checker|PRIME]]

| S NO |  INPUT  |                  OUTPUT                  |
| :--: | :-----: | :--------------------------------------: |
|  1   | 197<br> | True `(197, 971, and 719 are all prime)` |
|  2   |   23    |       False `(32 is not a prime)`        |
|  3   |   37    |    True `(37 and 73 are both prime)`     |
```c
#include <stdio.h>
#include <math.h>

int is_prime(int n) {
    if (n <= 1)
        return 0;
    if (n <= 3)
        return 1;
    for (int i = 2; i <= sqrt(n); i++) {
        if (n % i == 0)
            return 0;
    }
    return 1;
}

int is_circular_prime(int n) {
    int digits = floor(log10(abs(n))) + 1;
    int power = pow(10, digits - 1);
    
    int temp = n;
    for (int i = 0; i < digits; i++) {
        if (!is_prime(temp))
            return 0;
        int last = temp % 10;
        temp = (last * power) + (temp / 10);
    }
    return 1;
}

int main() {
    int n;
    scanf("%d", &n);
    
    if (is_circular_prime(n))
        printf("True");
    else
        printf("False");
    
    return 0;
}

```
---