>***Your function should be capable of quickly determining if two words are
anagrams, regardless of letter case or spaces.***

| S NO |                 INPUT                 | OUTPUT |
| :--: | :-----------------------------------: | :----: |
|  1   |         "listen"<br>"silent"          |  True  |
|  2   | "Slot machines"<br>"Cash lost in 'em" |  True  |
```c
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int is_anagram(char *s1, char *s2) {
    int hash[256] = {0};
    
    for (int i = 0; s1[i] != '\0'; i++) {
        if (isalnum(s1[i])) {
            hash[tolower(s1[i])]++;
        }
    }
    
    for (int i = 0; s2[i] != '\0'; i++) {
        if (isalnum(s2[i])) {
            hash[tolower(s2[i])]--;
        }
    }
    
    for (int i = 0; i < 256; i++) {
        if (hash[i] != 0) {
            return 0;
        }
    }
    return 1;
}

int main() {
    char s1[100];
    fgets(s1, sizeof(s1), stdin);
    s1[strcspn(s1, "\n")] = '\0'; // Remove newline character
    
    char s2[100];
    fgets(s2, sizeof(s2), stdin);
    s2[strcspn(s2, "\n")] = '\0'; // Remove newline character
    
    if (is_anagram(s1, s2)) {
        printf("True\n");
    } else {
        printf("False\n");
    }
    
    return 0;
}

```
---