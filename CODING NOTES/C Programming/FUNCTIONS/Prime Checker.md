>***you need to verify if a given number is prime to ensure security of generated keys. The function should be accurate and efficient for large numbers***

| S NO | INPUT | OUTPUT |
| :--: | :---: | :----: |
|  1   | 1001  | False  |
|  2   |  17   |  True  |
```c
#include <stdio.h>

int isprime(int n) {
    if (n <= 1) return 0;
    if (n <= 3) return 1;
    if (n % 2 == 0 || n % 3 == 0) return 0;
    for (int i = 5; i * i <= n; i += 6) {
        if (n % i == 0 || n % (i + 2) == 0) return 0;
    }
    return 1;
}

int main() {
    int n;
    scanf("%d", &n);
    
    if (isprime(n)) {
        printf("True\n");
    } else {
        printf("False\n");
    }
    
    return 0;
}

```
---