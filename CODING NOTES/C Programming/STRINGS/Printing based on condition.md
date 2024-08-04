### ***1. NON ALPHABETIC CHARACTERS***###

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
---
### ***2. CAPITALIZING FIRST WORD***###

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
---
### ***3. PRINTING ALTERNATIVE CHARACTERS IN STRING[IN REVERSE]***###

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
---
### ***4. PRINTING STRINGS WITH ODD/EVEN INDEX[2D]***###

```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int main(){
  int n;
  scanf("%d",&n);
  
  char s[n][100];
  for(int i=0;i<n;i++){
    scanf("%s",s[i]);
  }
  
  for(int i=0;i<n;i++){
    if(i%2 == 0){
      printf("%s\n",s[i]);
	    }
	    //printf("\n");
	}
}
```
---
### ***5. REVERSING STRING AT ODD/EVEN INDEX[2D]***###

```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int main(){
  int n;
  scanf("%d",&n);
  
  char s[n][100];
  for(int i=0;i<n;i++){
    scanf("%s",s[i]);
  }
  
  for(int i=0;i<n;i++){
    if(i%2 == 0){
      for(int j=strlen(s[i])-1;j>=0;j--){
        printf("%c",s[i][j]);
      }
      printf("\n");
    }
    else  printf("%s\n",s[i]);
  }
}
```
---
### ***6. REPLACING LAST CHARACTER WITH ANOTHER CHARACTER***###

```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int main(){
  char s[100];
  fgets(s,sizeof(s),stdin);
  s[strcspn(s,"\n")]='\0';
  char ch;
  scanf("%c",&ch);
  s[strlen(s)-1] = ch;
  printf("%s",s);
}
```
---
### ***7. REPLACING ALL THE OCCURANCE OF A CHARACTER WITH ANOTHER CHARACTER***###

```c
#include<stdio.h>
#include<string.h>

int main(){
  char str[100];
  fgets(str,sizeof(str),stdin);
  char val;
  scanf("%c",&val);
  char f;
  scanf(" %c",&f);
  
  for(int i=0;i<strlen(str);i++){
    if(str[i]== val)
    {
      str[i] = f;
    }
  }
  printf("%s",str);
}
```
---
### ***8. REPLACING FIRST OCCURANCE OF CHARACTER WITH ANOTHER CHARACTER***###

```C
#include<stdio.h>
#include<string.h>

int main(){
  char str[100];
  fgets(str,sizeof(str),stdin);
  char val;
  scanf("%c",&val);
  char f;
  scanf(" %c",&f);
  
  for(int i=0;i<strlen(str);i++){
    if(str[i]== val)
    {
      str[i] = f;
      break;
    }
  }
  printf("%s",str);
}
```
---
### ***9. REVERSING WORDS***###

```C
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int main(){
  char s[100];
  fgets(s,sizeof(s),stdin);
  s[strcspn(s,"\n")]='\0';
  
  char * newarr[100];
  char * token = strtok(s," ");
  int j=0;
  while(token!=NULL){
    newarr[j++] = token;
    token = strtok(NULL," ");
  }
  
  for(int i=j-1;i>=0;i--){
    printf("%s",newarr[i]);
    if(i<j)  printf(" ");
  }
  
}
```
---