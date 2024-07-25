```C
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int isprime(int x){
  if(x<=1)  return 0;
  if(x==3)  return 1;
  for(int i=2;i<x/2;i++){
    if(x%i == 0)  return 0;
  }
  return 1;
}


int main(){
  char s[100];
  fgets(s,sizeof(s),stdin);
  s[strcspn(s,"\n")]='\0';
  char temp[100];
  int  j=0;
  for(int i=0;i<strlen(s);i++){
    if(s[i]!= ' ')
    temp[j++] = s[i];
  }
  
  int x = strlen(temp);
  printf("%d\n",x);
  if(isprime(x))  printf("prime");
  else  printf("not a prime");
}
```