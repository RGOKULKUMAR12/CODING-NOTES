>***Given a string `s`, print all possible permutations of the string.***

| S NO | INPUT |                 OUTPUT                 |
| :--: | :---: | :------------------------------------: |
|  1   |  AB   |                AB<br>BA                |
|  2   |  ABC  | ABC<br>ACB<br>BAC<br>BCA<br>CBA<br>CAB |
|  3   |  12#  | 12#<br>1#2<br>21#<br>2#1<br>#21<br>#12 |
```c
#include<string.h>
#include<stdio.h>

void swap(char * x, char * y){
  char temp = *x;
  *x = *y;
  *y = temp;
}

void permutation(char * str,int s,int e){
  if (s == e)
  {
    printf("%s\n",str);
    return 0;
  }
  for(int i=s;i<=e;i++){
  swap(&str[s],&str[i]);
  permutation(str,s+1,e);
  swap(&str[s],&str[i]);
  }
}

int main()
{
  char str[100];
  fgets(str,sizeof(str),stdin);
  int n = strlen(str);
  
  permutation(str,0,n-1);
}
```
---