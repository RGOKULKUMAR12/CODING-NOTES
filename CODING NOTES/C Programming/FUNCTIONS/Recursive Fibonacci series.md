***function needs to efficiently compute Fibonacci numbers up to a large index requested by the user.***

| S NO | INPUT | OUTPUT |
| :--: | :---: | ------ |
|  1   |   6   | 8      |
|  2   |  10   | 55     |
|  3   |   0   | 0      |
```c
#include<stdio.h>

int fib(int n){
  if(n==0)
    return 0;
  if(n==1 || n==2)
    return 1;
  
  return (fib(n-1) + fib(n-2));
}

int main(){
  
  int n;
  scanf("%d",&n);
  
  int x = fib(n);
  printf("%d",x);
}
```

*RECURSIVE EXPLANATION*

![image](https://github.com/user-attachments/assets/9aa1da02-e7ad-4e00-a5db-4f9d10cf7d7c)

