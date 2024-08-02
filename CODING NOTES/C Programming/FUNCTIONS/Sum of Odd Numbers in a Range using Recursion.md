>***program to calculate the sum of all odd numbers within a given range***

| S NO | INPUT    | OUTPUT |
| ---- | -------- | ------ |
| 1    | 10<br>20 | 75     |
| 2    | 1<br>10  | 25     |
| 3    | 5<br>15  | 60     |

```c
#include<stdio.h>
#include<string.h>

int odd(int n,int n2){
  if(n<n2){
    return n + odd(n+2,n2);
  }
  return 0;
}

int main(){
  int n1,n2;
  
  scanf("%d",&n1);
  scanf("%d",&n2);
  int max;
  if(n1%2 == 0)
    max = odd(n1+1,n2);
  else
    max = odd(n1,n2);
    
  printf("%d",max);  
}
```
---
