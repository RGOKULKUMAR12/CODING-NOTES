### ***1. FIRST OCCURANCE OF A CHARACTER*** ###

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
---
### ***2. FINDING LONGEST AND SMALLEST STRING[2D]*** ###

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
---
### ***3. SECOND LARGEST STRING[2D]*** ###

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
---
### ***4. FINDING NO OF PERSONS ABOVE AGE 60*** ###

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

| INPUT                                                   | OUTPUT |
| :------------------------------------------------------ | ------ |
| 3<br>1234567890M625<br>1234567890F266<br>1324567890M562 | 1      |

---
### ***5. FIRST CAPITAL CHARACTER IN STRING*** ###

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
---
### ***6. FINDING INDEX OF THE WORD*** ###

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
---
### ***7. FINDING ALL INDEX OF THE WORD*** ###

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
---
### ***8.  SUM OF THE DIGITS IN AN STRING AND REVERSE IT*** ###

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
---
### ***9. FINDING FIRST NON-REPEATING CHARACTER*** ###

*9.1 USING HASH*

```C
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int main()
{
  char str[100];
  fgets(str,sizeof(str),stdin);
  
  int hash[256]={0};
  
  for(int i=0;i<strlen(str);i++){
    hash[str[i]]++;
  }
  
  for(int i=0;i<strlen(str);i++){
    if(hash[str[i]] == 1)
    {
      printf("%c",str[i]);
      break;
    }
  }
}
```
---
*9.2. WITHOUT HASH* 

```C
#include<stdio.h>
#include<string.h>

int main(){
  
  char str[100];
  fgets(str,sizeof(str),stdin);
  
  char arr[100] = {0};
  
  int x = strlen(str);
  for(int i=0;i<x;i++){
    for(int j=i+1;j<x;j++){
      if(str[i] == str[j]){
        arr[i] = 1;
        arr[j] = 1;
      }
    }
  }
  
  for(int i=0;i<x;i++){
      if(arr[i]==0) 
      {
        printf("%c",str[i]);
        break;
      }
  }
}
```
---
### ***10. FINDING LAST OCCURANCE OF A CHARACTER*** ###

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
  
  while(i<length)
  {
    if(str[i] == val) index = i;
    i++;
  }
  
  printf("the last occurance of %c is in %d",val,index);
}
```
---
### ***11. FINDING FIRST OCCURANCE OF A CHARACTER*** ###

```C
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
  
  while(i<length)
  {
    if(str[i] == val) index = i;
    break;
  }
  printf("the first occurance of %c is in %d",val,index);
}
```
---
### ***12. MAX OCCURANCE OF THE CHARACTER*** ###

```C
#include<stdio.h>
#include<string.h>
#include<limits.h>

int main(){
 
 char temp[100];
 fgets(temp,sizeof(temp),stdin);
 char str[100];
 int j=0;
 
 for(int i=0;i<strlen(temp);i++){
   if(temp[i] != ' '){
      str[j++] = temp[i];
   }
 }
 
 int visited[100] = {0};
 
 int max = INT_MIN;
 int char_max = CHAR_MAX;
 
 for(int i=0;i<strlen(str);i++){
   if(visited[i] == 0){
     int count = 1;
     for(int j=i+1;j<strlen(str);j++){
       if(str[i] == str[j]){
         count++;
         visited[j] = 1;
       }
     }
     if(count > max ){
       max = count;
       char_max = str[i];
     }
   }
 }
 printf("%c has occured %d times",char_max,max);
}
```
---
### ***13. MINIMUM OCCURANCE OF A CHARACTER*** ###

```c
#include<stdio.h>
#include<string.h>
#include <limits.h>
int main()
{
  char str[100];
  fgets(str,sizeof(str),stdin);
  
  str[strcspn(str,"\n")] = '\0';
  
  char val;
  int min = INT_MAX;

  int visited[100] = {0};
  
  for (int i=0;i<strlen(str);i++)
  {
    
    if(visited[i] == 0)
    {
      int count = 1;
      
      for(int j=i+1;j<strlen(str);j++)
      {
        if(str[i] == str[j])
        {
          count++;
          visited[j] = 1;
        }
      }
      if(count < min ) 
      {
        min_char = str[i];
        min = count;
      }
    }
  }
  printf("%c has occured %d times\n",min_char,min);

  return 0;
}
```
---
### ***14. INDEX OF ALL THE OCCURANCE OF THE CHARCTER***  ###

```C
#include<stdio.h>
#include<string.h>

int main()
{
  char str[100];
  fgets(str,sizeof(str),stdin);
  
  str[strcspn(str,"\n")] = '\0';
  
  char target;
  scanf("%c",&target);
  
  int temp=0;
  for (int i=0;i<strlen(str);i++)
  {
    if(str[i] == target){
      printf("%d ",i);
      temp++;
    }
  }
  printf("\n%d",temp);
  return 0;
}
```
---
### ***15. TOTAL NO OF ALPHABETS/NON ALPHABETS*** ###

```C
#include <stdio.h>
#include <string.h>
int main()
{
  char str[100];
  fgets(str,sizeof(str),stdin);
  
  int count =1;
  for(int i=0;str[i]!=0;i++)
  {
  //--------REMOVE '!' TO FIND NON-ALPHA COUNT
    if(!(str[i] ==' ' || str[i] == '\n' || str[i] == '\t'))
    {
      count++;
    }
  }
  printf("%d",count);
}
```
---
### ***16. FINDING COUNT OF VOWELS/CONSONENTS*** ###

```C
#include <stdio.h>
#include <string.h>

int main()
{
  char str[100];
  fgets(str,sizeof(str),stdin);
  int count=0,count1 = 0;
  
  for(int i=0;str[i]!=0;i++){
    tolower(str[i]);
    if(!(str[i]=='a'|| str[i]=='e'||  str[i]=='i'|| str[i]=='o'|| str[i]=='u'))
    {
      //printf("%c",str[i]);
      count++;
      continue;
    }
    else{
	    printf("%c",str[i]);
	    count1++;
    }
  }
  printf("\n%d\n%d",count,count1);
}

```
---

