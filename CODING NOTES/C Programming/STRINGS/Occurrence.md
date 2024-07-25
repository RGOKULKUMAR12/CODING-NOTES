***1. FIRST OCCURANCE OF A CHARACTER

```C
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int main(){
  char s[100];
  fgets(s,sizeof(s),stdin);
  s[strcspn(s,"\n")]='\0';
  int visited[100] = {0};
  int count;
  for(int i=0;i<strlen(s);i++){
    if(visited[i] == 0){    
      count =0;
      for(int j=i+1;j<strlen(s);j++){
        if(s[i] == s[j]){
          count++;
          visited[j] = 1;
        }
      }
    }
    if(count == 0){
      printf("%c",s[i]);
      break;
	  }
	}
}
```
