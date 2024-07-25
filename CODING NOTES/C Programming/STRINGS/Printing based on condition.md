***1. NON ALPHABETIC CHARACTERS

```C
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int main(){
  char s[100];
  fgets(s,sizeof(s),stdin);
  s[strcspn(s,"\n")]='\0';
  
  for(int i=0;i<strlen(s);i++){
    //if(!((s[i]>='a' && s[i]<='z') || (s[i]>='A' && s[i] <='Z')))
      if(!(isalpha(s[i])))
      printf("%c",s[i]);
  }
}
```

***2. CAPITALIZING FIRST WORD

```C
#include<stdio.h>
#include<string.h>
#include<ctype.h>

void cap(char * s){
  int inword = 0;
  for(int i=0;i<strlen(s);i++){
    if(isalpha(s[i])){
      if(!inword){
        s[i] = toupper(s[i]);
        inword = 1;
      }
      else{
        s[i] = tolower(s[i]);
      }
    }
    else{
      inword = 0;
    }
  }
}
int main(){
  char s[100];
  fgets(s,sizeof(s),stdin);
  s[strcspn(s,"\n")]='\0';
  
  cap(s);
  printf("%s",s);
}
```
***3. PRINTING ALTERNATIVE CHARACTERS IN STRING[IN REVERSE]

```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int main(){
  char s[100];
  fgets(s,sizeof(s),stdin);
  s[strcspn(s,"\n")]='\0';
  
  for(int i=strlen(s)-1;i>=0;i--){
    if(i%2 != 0)  printf("%c",s[i]);
  }
}
```
