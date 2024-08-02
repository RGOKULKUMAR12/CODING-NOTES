> ***You are developing a scientific calculator application that requires computing powers of numbers. The function should accurately handle both positive and negative exponents.***

| S NO | INPUT  | OUTPUT |
| :--: | :----: | :----: |
|  1   | 2<br>5 |   32   |
|  2   | 3<br>4 |   81   |
```c
#include <stdio.h>
#include <math.h>

int power(int base, int exponent) {
    return pow(base, exponent);
}

int main() {
    int base, exponent;
    scanf("%d", &base);
    scanf("%d", &exponent);
    
    if (exponent < 0) {
        printf("invalid");
        return 0;
    }
    
    int result = power(base, exponent);
    printf("%d", result);
    
    return 0;
}

```
---