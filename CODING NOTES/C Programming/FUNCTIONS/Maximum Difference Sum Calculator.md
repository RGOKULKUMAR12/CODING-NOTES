>***Given `n` points on a 2D plane, where each point is represented by its x and y coordinates, write a program to calculate the sum of the maximum of the absolute differences between consecutive points in terms of their x and y coordinates***

| S NO | INPUT                          | OUTPUT |
| ---- | ------------------------------ | ------ |
| 01   | 3<br>1 2<br>4 6<br>7 10        | 8      |
| 02   | 4<br>1 4<br>-1 3<br>3 7<br>6 6 | 9      |

```c
#include <stdio.h>
#include <string.h>
#include <math.h>

// Maximum Difference Sum Calculator Program

int find_max(int n, int s[n][2]) {
    int sum = 0;
    for (int i = 0; i < n - 1; i++) {
        sum += fmax(abs(s[i][0] - s[i + 1][0]), abs(s[i][1] - s[i + 1][1]));
    }
    return sum;
}

int main() {
    int n;
    scanf("%d", &n);
    int s[n][2];
    
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < 2; j++)
            scanf("%d", &s[i][j]);
    }
    
    int sum = find_max(n, s);
    
    printf("%d", sum);
    
    return 0;
}

```