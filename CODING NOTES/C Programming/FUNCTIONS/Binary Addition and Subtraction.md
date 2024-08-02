>***Given two binary strings, write a program to convert them to decimal, calculate their sum and difference in decimal, and then convert these results back to binary.***


| S NO | INPUT                | OUTPUT                                                                                                   |
| ---- | -------------------- | -------------------------------------------------------------------------------------------------------- |
| 01   | 1010<br>110<br>      | SUM IN DECIMAL:*12*<br>DIFF IN DECIMAL:*4*<br>SUM IN BINARY:*00001100*<br>DIFF IN BINARY:*00000100*<br>  |
| 02   | 00101001<br>00001010 | SUM IN DECIMAL: *51*<br>DIFF IN DECIMAL: *31*<br>SUM IN BINARY: *00110011*<br>DIFF IN BINARY: *00011111* |
```c
#include <stdio.h>
#include <string.h>
#include <math.h>

#define MAX 8

// Binary and Decimal Conversion Program

int deci_to_bin(int n, char *str) {
    int i = 0;
    while (n > 0) {
        str[i++] = (n % 2) + '0';
        n /= 2;
    }
    str[i] = '\0';
    
    int len = strlen(str);
    for (int i = 0; i < len / 2; i++) {
        char temp = str[i];
        str[i] = str[len - 1 - i];
        str[len - 1 - i] = temp;
    }
    
    if (len < MAX) {
        memmove(str + (MAX - len), str, len + 1);
        memset(str, '0', MAX - len);
    }
}

int bi_to_dec(char *str) {
    int len = strlen(str);
    int decimal = 0;
    for (int i = 0; i < len; i++) {
        if (str[len - 1 - i] == '1') {
            decimal += pow(2, i);
        }
    }
    return decimal;
}

int main() {
    char b[100];
    fgets(b, sizeof(b), stdin);
    b[strcspn(b, "\n")] = '\0';
    
    char b2[100];
    fgets(b2, sizeof(b2), stdin);
    b2[strcspn(b2, "\n")] = '\0';
    
    int num1 = bi_to_dec(b);
    int num2 = bi_to_dec(b2);
    
    int sum = num1 + num2;
    int diff = num1 - num2;
    
    printf("SUM IN DECIMAL: %d\n", sum);
    printf("DIFF IN DECIMAL: %d\n", diff);
    
    char bi1[100] = {0};
    char bi2[100] = {0};
    
    if (sum > 0) {
        deci_to_bin(sum, bi1);
    } else {
        strcpy(bi1, "0");
    }
    
    if (diff >= 0) {
        deci_to_bin(diff, bi2);
    } else {
        strcpy(bi2, "invalid");
    }
    
    printf("SUM IN BINARY: %s\n", bi1);
    printf("DIFF IN BINARY: %s", bi2);
    
    return 0;
}

```
---