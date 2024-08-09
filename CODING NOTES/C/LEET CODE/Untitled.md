```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
#include<stdbool.h>

int main(){
  char str[100];
  fgets(str,sizeof(str),stdin);
  str[strcspn(str,"\n")]='\0';
  char newarr[100];
  int j=0;
  for(int i=0;i<strlen(str);i++){
      if(i == 0  || !(str[i]==' ' && str[i-1]==' ')){
          newarr[j++] = str[i];
      }
        
  }
  char * token = strtok(newarr," ");
  char * last = NULL;
  while(token!=NULL){
      last = token;
      token = strtok(NULL," ");
  }
   int lwn = last ? strlen(last) : 0;
  printf("%d",lwn);
  
  
}
```