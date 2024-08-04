### ***1. DELETING DUPLICATE WORD (DUPLICATE WORD NOT GIVEN)*** ###

```c
#include <stdio.h>
#include <string.h>

int main() {
    char arr[100];
    scanf(" %[^\n]s", arr);
    
    char *newarr[100];
    int index = 0;
    char *token = strtok(arr, " ");
    
    while (token != NULL) {
        newarr[index++] = token;
        token = strtok(NULL, " ");
    }
    
    for (int i = 0; i < index; i++) {
        int flag = 0;
        for (int j = 0; j < i; j++) {
            if (strcmp(newarr[i], newarr[j]) == 0) {
                flag = 1;
                break;
            }
        }
        if (!flag) {
            printf("%s ", newarr[i]);
        }
    }
    printf("\n"); // adding newline for better output formatting
    
    return 0;
}
```
---
### ***2. REMOVING ALL THE GIVEN WORD***###

```C
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int main(){
  char s[100];
  fgets(s,sizeof(s),stdin);
  s[strcspn(s,"\n")]='\0';
  
  char s2[100];
  fgets(s2,sizeof(s2),stdin);
  s2[strcspn(s2,"\n")]='\0';
  
  /*char * pos;
  int x2 = strlen(s2);
  
  while((pos = strstr(s,s2))!=NULL){
    memmove(pos,pos+x2,strlen(pos+x2)+1);
  }
  printf("%s ",s);*/
  
  char * token = strtok(s," ");
  
  while(token!=NULL){
    int flag = 0;
    if(strcmp(token,s2)==0 && !flag)
      flag = 1;
    else if(!flag) 
    printf("%s ",token);
    token = strtok(NULL," ");
  }
}
```
---
### ***3. REMOVING FIRST OCCURANCE OF A WORD***###

>[!warning]
**Open test case is wrong in ps**

```c
#include <stdio.h>
#include<string.h>
int main()
{
    
  char str[1000];
  fgets(str,sizeof(str),stdin);
  
  str[strcspn(str,"\n")]='\0';
  char str2[1000];
  fgets(str2,sizeof(str2),stdin);
  str[strcspn(str,"\n")]='\0';
  
  int x2 = strlen(str2);
  int index=-1;
 
  char * pos = strstr(str,str2);
  if(pos!=NULL){
    index = pos - str;
  }
  for(int i=index;i<strlen(str);i++){
    str[i] = str[i+x2];
  }
  
  //-----------IF THEY WANTED TO REMOVE THE EXTRA SPACE-------
  /*int j=0;
  char temp[100];
  
  for(int i=0;i<strlen(str);i++){
    if(!(str[i]==' ' && (str[i+1] == ' '|| str[i+1] =='\0'||str[i+1] == '\n' )))  temp[j++] = str[i];
  }
  temp[j] = '\0';*/
  printf("%s",str);
}
```
---
### ***4. REMOVING LAST OCCURANCE OF THE WORD*** ###

```c
#include <stdio.h>
#include<string.h>

int main()
{
  char str[100];
  fgets(str,sizeof(str),stdin);
  char str2[100];
  fgets(str2,sizeof(str2),stdin);
  
  int length = strlen(str2);
  
  char * pos = strstr(str,str2);
  char * last_pos = NULL;
  while(pos!=NULL){
    last_pos = pos;
    pos = strstr(pos+1,str2); 
  }
  int index = -1;
  if(last_pos!=NULL){
    index= last_pos - str;
  }
  else  printf("not");

  for(int i=index;i<strlen(str)+1;i++){
    str[i] = str[i+length];
  }
  //--------IF ASKED TO REMOVE EXTRA SPACES------
  /*for (int i = strlen(str) - 1; i >= 0 && str[i] == ' '; i--) {
        str[i] = '\0';
    }*/
  printf("%s",str);

}
```
---
### ***5.REMOVING EXTRA WHITESPACES***###

```C
#include<stdio.h>
#include<string.h>

int main()
{
  char str[100];
  char result[1000]="";
  fgets(str,sizeof(str),stdin);
  
  //-----------METHOD-1--------------------
  char * token;
  token = strtok(str," ");
  
  while(token!=NULL)
  {
    printf("%s ",token);  
    token = strtok(NULL," ");
  }
  //-------------METHOD-2-------------- 
  int j=0;
  char temp[100];
  for(int i=0;i<strlen(str);i++){
    if(!(str[i]==' ' && (str[i+1] == ' '|| str[i+1] =='\0'||str[i+1] == '\n' )))
	    temp[j++] = str[i];
  }
  temp[j] = '\0';
  printf("%s",str);
}
```
---
### ***6. REMOVING LEADING WHITESPACES***###

```c
#include<stdio.h>
#include<string.h>

int main(){
  
  char str[100];
  fgets(str,sizeof(str),stdin);
  str[strcspn(str,"\n")] = '\0';
  
  int index=0;
  
  while(str[index]==' '|| str[index] == '\t' || str[index] == '\n') 
		  index++;
  if(index!=0)  
  {
    for(int i=index;i<strlen(str);i++){
      printf("%c",str[i]);
    }
  }
  else  printf("%s",str);
}
```
---
### ***7. REMOVING TRAILING WHITESPACE***###

```c
#include<stdio.h>
#include<string.h>

int main(){
  
  char str[100];
  fgets(str,sizeof(str),stdin);
  str[strcspn(str,"\n")] = '\0';
  
  int index=strlen(str)-1;
  
  while(str[index]==' '|| str[index] == '\t' || str[index] == '\n')
	  index--;
  if(index!=0)  
  {
    for(int i=0;i<=index;i++){
      printf("%c",str[i]);
    }
  }
  else  printf("%s",str);
}
```
---
### ***8. REMOVING BOTH LEADING AND TRAILING WHITESPACES***###

```c
#include<stdio.h>
#include<string.h>

int main()
{
  char str[100];
  fgets(str,sizeof(str),stdin);
  str[strcspn(str,"\n")] = '\0';
  
  int index=0;
  while(str[index] == ' ' ||str[index] == '\t' ||str[index] == '\n')
    index++;
    
  int index2 = strlen(str)-1;
  while(str[index2] == ' ' ||str[index2] == '\t' ||str[index2] == '\n') 
	   index2--;
  
  for(int i=index;i<=index2;i++)
	  printf("%c",str[i]);
}
```
---
### ***9. REMOVING DUPLICATE CHARACTERS***###

```C
#include<stdio.h>
#include<string.h>

int main()
{
  char str[100];
  fgets(str,sizeof(str),stdin);
  
  int length = strlen(str);
  for(int i=0;i<length;i++){
    for(int j=i+1;j<length;j++){
      if(str[i] == str[j]){
        for(int k=j;k<length;k++){
          str[k] = str[k+1];
	      }
	      length--;
	      j--;
	    }
	  }
	}
	printf("%s",str);
}
```
---
### ***10. REMOVING LAST OCCURANCE OF A CHARACTER*** ###

```c
#include<stdio.h>
#include<string.h>

int main()
{
  char str[100],val;
  fgets(str,sizeof(str),stdin);
  str[strcspn(str,"\n")]='\0';
  scanf("%c",&val);
  
  int length = strlen(str);
  int i=0;
  int index = -1;
   
  while(i<length){
    if(str[i] == val) index = i;
    i++;
  }
  for (int i=index;str[i]!='\0';i++)  str[i] = str[i+1];
  printf("%s",str);
}
```
---
### ***11. REMOVING FIRST OCCURANCE OF A CHARACTER***###

```c
#include<stdio.h>
#include<string.h>

int main()
{
  char str[100],val;
  fgets(str,sizeof(str),stdin);
  str[strcspn(str,"\n")]='\0';
  scanf("%c",&val);
  
  int length = strlen(str);
  int i=0;
  
  while(i<length && str[i] != val)  i++;
  while(i<length) 
  {
    str[i] = str[i+1];
    i++;
  }
  str[i] = '\0';
  
  printf("%s",str);
}
```
---