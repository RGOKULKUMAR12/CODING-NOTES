***1. LEFT ROTATE BY 'K' TERMS

```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>

void leftrotate(char *s,int k){
  int len = strlen(s);
  k = k%len;
  char temp[len];
  
  strncpy(temp,s+len-k,k);
  strncpy(temp+k,s,len-k);
  
  temp[len+1] = '\0';
  strcpy(s,temp);
}

int main(){
  char s[100];
  fgets(s,sizeof(s),stdin);
  s[strcspn(s,"\n")]='\0';
  int k;
  scanf("%d",&k);
  leftrotate(s,k);
  printf("%s",s);
}
```

***2. RIGHT ROTATE BY 'K' TERMS***

```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>

void rightrotate(char *s,int k){
  int len = strlen(s);
  k = k%len;
  char temp[len];
  
  strncpy(temp,s+k,len-k);
  strncpy(temp+len-k,s,k);
  
  temp[len+1] = '\0';
  strcpy(s,temp);
}

int main(){
  char s[100];
  fgets(s,sizeof(s),stdin);
  s[strcspn(s,"\n")]='\0';
  int k;
  scanf("%d",&k);

  rightrotate(s,k);
  
  printf("%s",s);
  
}
```
