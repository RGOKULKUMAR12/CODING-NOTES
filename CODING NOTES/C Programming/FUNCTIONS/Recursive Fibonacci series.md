***function needs to efficiently compute Fibonacci numbers up to a large index requested by the user.***

| S NO | INPUT | OUTPUT |
| :--: | :---: | ------ |
|  1   |   6   | 8      |
|  2   |  10   | 55     |
|  3   |   0   | 0      |
```c
#include<stdio.h>

int fibannoci(int n){
  if(n==0)
    return 0;
  if(n==1 || n==2)
    return 1;
  
  return (fibannoci(n-1) + fibannoci(n-2));
}

int main(){
  
  int n;
  scanf("%d",&n);
  
  int x = fibannoci(n);
  printf("%d",x);
}
```

*RECURSIVE EXPLANATION*

![[../../IMAGES/Pasted image 20240726122813.png]]
