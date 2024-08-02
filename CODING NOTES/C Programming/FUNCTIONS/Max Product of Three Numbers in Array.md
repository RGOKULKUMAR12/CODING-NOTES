>***Given an integer array , find three numbers whose product is maximum and return the maximum product.***

| S NO |   INPUT    | OUTPUT |
| :--: | :--------: | :----: |
|  1   |  [1,2,3]   |   6    |
|  2   | [1,2,3,4]  |   24   |
|  3   | [-1,-2,-3] |   -6   |

```c
#include <stdio.h>
#include <limits.h>
#include <math.h>

int find_max(int *arr, int n) {
    int first_max = INT_MIN;
    int second_max = first_max;
    int third_max = first_max;
    
    int first_min = INT_MAX;
    int second_min = first_min;
    
    for (int i = 0; i < n; i++) {
        if (arr[i] >= first_max) {
            third_max = second_max;
            second_max = first_max;
            first_max = arr[i];
        } else if (arr[i] >= second_max) {
            third_max = second_max;
            second_max = arr[i];
        } else if (arr[i] >= third_max) {
            third_max = arr[i];
        }
        
        if (arr[i] <= first_min) {
            second_min = first_min;
            first_min = arr[i];
        } else if (arr[i] <= second_min) {
            second_min = arr[i];
        }
    }

    int maax = fmax(first_max * second_max * third_max, first_min * second_min * first_max);

    return maax;
}

int main() {
    int n;
    scanf("%d", &n);
    int arr[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    int max = find_max(arr, n);
    printf("%d", max);
    
    return 0;
}

```
---