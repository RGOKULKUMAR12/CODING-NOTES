***1. CHECK WHETHER THE STRING IS PALINDROME OR NOT***

```c
#include <stdio.h>
#include <string.h>
int main()
{
  char str[100];
  fgets(str,sizeof(str),stdin);
  char str2[100];
  int j=0;
  for(int i=strlen(str)-1;i>=0;i--)
  {
    str2[j] = str[i];
    j++;
  }
  printf("reversed string: %s\n",str2);
  
  int res = strcmp(str,str2);
  
  if(res==0)  printf("palindrome");
  else  printf("not a palindrome");
  
}
```

***2. LONGEST PALINDROME SUBSTRING

```c
#include<stdio.h>
#include<string.h>
#include<stdbool.h>
#include<stdlib.h>

bool isvalid(char * s,int start,int e){
  while(start<e){
    if(s[start]!=s[e])  return false;
    start++;
    e--;
  }
  return true;
}

char * longestpalindrom(char * s){
  int len = strlen(s);
  int max = 0,ss;
  char * resStr = malloc((len+1) * sizeof(char));
  
  for(int i=0;i<len;i++){
    ss=0;
    for(int j=len-1;j>=i;j--){
      if(isvalid(s,i,j)){
        ss= j-i+1;
        if(ss > max){
          max = ss;
          strncpy(resStr,s+i,max);
          s[max] = '\0';
        }
      }
    }
  }
  return resStr;
}

int main(){
  char s[100];
  fgets(s,sizeof(s),stdin);
  
  char * result = longestpalindrom(s);
  printf("%s",result);
  free(result);
}
```

