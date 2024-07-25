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
***2. FINDING LONGEST AND SMALLEST STRING[2D]

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
  int large = 0;
  int large_pos = -1;
  int small = 100;
  int small_pos = -1;
  for(int i=0;i<n;i++){
    int x = strlen(s[i]);
    if(x>large){
      large = x;
      large_pos = i;
    }
    if(x<small){
      small = x;
      small_pos = i;
    }
  }
  printf("LARGEST:%s\nlength:%d index:%d",s[large_pos],large,large_pos);
  printf("\nSMALLEST:%s\nlength:%d index:%d",s[small_pos],small,small_pos);
}
```
***3. SECOND LARGEST STRING[2D]

```C
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
  int  max_count = 0;
  int second_count = 0;
  for(int i=0;i<n;i++){
    int x = strlen(s[i]);
    if(x>max_count){
      second_count = max_count;
      max_count = x;
     }
    }
    printf("%d",second_count);
  }
```
***4. FINDING NO OF PERSONS ABOVE AGE 60

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
  int count =0;
  for(int i=0;i<n;i++){
    if(s[i][11] >='6')  count++;
  }
  
  printf("%d",count);
}
```

| INPUT                                                    | OUTPUT |
| :------------------------------------------------------- | ------ |
| 3<br>1234567890M625<br>1234567890F2666<br>1324567890M562 | 1      |
***5. FIRST CAPITAL CHARACTER IN STRING

```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int main(){
  char s[100];
  fgets(s,sizeof(s),stdin);
  s[strcspn(s,"\n")]='\0';
  
  
  for(int i=0;i<strlen(s);i++){
    if(s[i]>='A' && s[i]<='Z'){
      printf("%c",s[i]);
      break;
    }
  }
}
```
***6. FINDING INDEX OF THE WORD

```c
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
  
  char * pos = strstr(s,s2);
  
  if(pos!=NULL){
    int index = pos - s;
    printf("found at index:%d\n",index); 
  }  
}
```
***7. FINDING ALL INDEX OF THE WORD

```c
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
  
  char * pos = strstr(s,s2);
  
  while(pos!=NULL){
    int index = pos - s;
    printf("found at index:%d\n",index);
    pos = strstr(pos+1,s2);
  }
  
}
```
***8.  SUM OF THE DIGITS IN AN STRING AND REVERSE IT

```C
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int main(){
  char s[100];
  fgets(s,sizeof(s),stdin);
  s[strcspn(s,"\n")]='\0';
  
  int count =0;
  
  for(int i=0;i<strlen(s);i++){
    if(s[i]>='0' && s[i] <='9'){
      count+=s[i]-'0';
    }
  }
  printf("%d\n",count);
  char temp[100];
  sprintf(temp,"%d",count);
  for(int i=strlen(temp)-1;i>=0;i--){
    printf("%c",temp[i]);
  } 
}
```
