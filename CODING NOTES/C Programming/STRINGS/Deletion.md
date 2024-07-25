***1. DELETING DUPLICATE WORD (DUPLICATE WORD NOT GIVEN)

```c
#include <stdio.h>
#include <string.h>

int main() {
    char arr[100];
    scanf(" %[^\n]s", arr);
    
    char *newarr[100];
    int index = 0;
    char *token = strtok(arr, " ");
    
    while (token != NULL) {
        newarr[index++] = token;
        token = strtok(NULL, " ");
    }
    
    for (int i = 0; i < index; i++) {
        int flag = 0;
        for (int j = 0; j < i; j++) {
            if (strcmp(newarr[i], newarr[j]) == 0) {
                flag = 1;
                break;
            }
        }
        if (!flag) {
            printf("%s ", newarr[i]);
        }
    }
    printf("\n"); // adding newline for better output formatting
    
    return 0;
}
```
