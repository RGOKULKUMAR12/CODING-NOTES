>***Given two integers `n` and `n2`, write a program to find and print all pairs of prime numbers between `n` and `n2` (inclusive) that are anagrams of each other.***

| S NO |    INPUT     |       OUTPUT       |
| :--: | :----------: | :----------------: |
|  1   | 10<br>50<br> | 13   31<br>17   71 |
|  2   |   10<br>40   |      13   31       |
```c
#include <stdio.h>
#include <string.h>

// Prime Anagram Pair Finder Program

int is_prime(int n) {
    if (n <= 1)
        return 0;
    if (n <= 3)
        return 1;
    for (int i = 2; i <= n / 2; i++) {
        if (n % i == 0)
            return 0;
    }
    return 1;
}

int is_anagram(int n, int n2) {
    char num1[100];
    char num2[100];
    int hash[256] = {0};
    
    sprintf(num1, "%d", n);
    sprintf(num2, "%d", n2);
    
    int x = strlen(num1);
    if (x != strlen(num2))
        return 0;
    
    for (int i = 0; i < x; i++) {
        hash[num1[i]]++;
        hash[num2[i]]--;
    }
    
    for (int i = 0; i < 256; i++) {
        if (hash[i] != 0)
            return 0;
    }
    return 1;
}

int main() {
    int n, n2;
    scanf("%d", &n);
    scanf("%d", &n2);
    
    for (int i = n; i <= n2; i++) {
        if (is_prime(i)) {
            for (int j = i + 1; j <= n2; j++) {
                if (is_prime(j) && is_anagram(i, j)) {
                    printf("%d %d\n", i, j);
                }
            }
        }
    }
    
    return 0;
}

```
---