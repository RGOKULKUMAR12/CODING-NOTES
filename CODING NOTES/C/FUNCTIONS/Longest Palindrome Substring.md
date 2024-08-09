>***Given a string find the longest palindrome substring*** 

| S NO | INPUT | OUTPUT |
| :--: | :---: | :----: |
|  1   | babad |  bab   |
|  2   | cbbd  |   bb   |
```c
#include <stdio.h>
#include <string.h>
#include <stdbool.h>
#include <stdlib.h>

bool isvalid(char *s, int start, int e) {
    while (start < e) {
        if (s[start] != s[e]) {
            return false;
        }
        start++;
        e--;
    }
    return true;
}

char *longestpalindrom(char *s) {
    int len = strlen(s);
    int max = 0, ss;
    char *resStr = malloc((len + 1) * sizeof(char));

    for (int i = 0; i < len; i++) {
        ss = 0;
        for (int j = len - 1; j >= i; j--) {
            if (isvalid(s, i, j)) {
                ss = j - i + 1;
                if (ss > max) {
                    max = ss;
                    strncpy(resStr, s + i, max);
                    resStr[max] = '\0';
                }
            }
        }
    }
    return resStr;
}

int main() {
    char s[100];
    fgets(s, sizeof(s), stdin);

    char *result = longestpalindrom(s);
    printf("%s", result);
    free(result);
}

```
---