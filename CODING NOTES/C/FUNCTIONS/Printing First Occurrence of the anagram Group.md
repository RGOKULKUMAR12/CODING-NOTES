>***Given a list of `n` strings, write a program to print the first occurrence anagram***

> [!Tip]
> - Check how to find : [[../STRINGS/Conditions#***7. ANAGRAM***|Anagram]]

[[../STRINGS/Finding something|Finding something]]

| S NO | INPUT                                       | OUTPUT               |
| ---- | ------------------------------------------- | -------------------- |
| 1    | 6<br>cat<br>dog<br>tac<br>god<br>act<br>odg | cat<br>dog<br>       |
| 2    | 5<br>listen<br>silent<br>dog<br>cat<br>tac  | listen<br>dog<br>cat |


```c
#include <stdio.h>
#include <string.h>

int is_anagram(char *str1, char *str2) {
    int hash[256] = {0};
    int x = strlen(str1);
    
    if (x != strlen(str2))
        return 0;
    
    for (int i = 0; i < x; i++) {
        hash[str1[i]]++;
        hash[str2[i]]--;
    }
    
    for (int i = 0; i < 256; i++) {
        if (hash[i] != 0)
            return 0;
    }
    
    return 1;
}

int main() {
    int n;
    scanf("%d", &n);
    
    char str[n][100];
    
    for (int i = 0; i < n; i++) {
        scanf("%s", str[i]);
    }
    
    int visited[100] = {0};
    
    for (int i = 0; i < n; i++) {
        if (visited[i] == 0) {
            printf("%s", str[i]);
            visited[i] = 1;
            for (int j = i + 1; j < n; j++) {
                if (is_anagram(str[i], str[j])) {
                    visited[j] = 1;
                }
            }
            printf("\n");
        }
    }
    
    return 0;
}
```

