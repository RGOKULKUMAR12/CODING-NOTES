***1. CHECK IF THE LENGTH OF A STRING IS PRIME OR NOT***

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
---
***2. CHECK WHETHER THE STRING IS PALINDROME OR NOT***

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
---
***3. LONGEST PALINDROME SUBSTRING***

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
---
***4. SWAPING ADJACENT CHARACTERS IN STRING***

```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int main(){
  char s[100];
  fgets(s,sizeof(s),stdin);
  s[strcspn(s,"\n")]='\0';
  int j = 1;
  for(int i=0;i<strlen(s);){
      
      if(j<strlen(s))
      {
        char temp = s[i];
        s[i] = s[j];
        s[j] = temp;
      }
    i+=2;
    j+=2;
    
  }
  printf("%s",s);
}
```
---
***5. LATEST VERSION***

```C
#include<stdio.h>
#include<string.h>
#include<ctype.h>

void v(char * s,int * sparts,int * size){
  char copy[100];
  strcpy(copy,s);
  char * token = strtok(copy,".");
  int count = 0;
  while(token!=NULL){
    sparts[count++] = atoi(token);
    token = strtok(NULL,".");
  }
  *size = count;
}

int versioncheck(char * s,char * s2){
  int sparts[100] = {0};
  int s2parts[100] = {0};
  int size1 = 0,size2 = 0;
  
  v(s,sparts,&size1);
  v(s2,s2parts,&size2);
  
  int max_size = size1>size2?size1:size2;
  
  
  for(int i=0;i<max_size;i++){
    if(sparts[i] > s2parts[i]){
      return -1;
    }
    else if (sparts[i] < s2parts[i]){
      return 1;
      
    }
    
  }
  return 0;
}

int main(){
  char s[100];
  fgets(s,sizeof(s),stdin);
  s[strcspn(s,"\n")]='\0';
  
  char s2[100];
  fgets(s2,sizeof(s2),stdin);
  s2[strcspn(s2,"\n")]='\0';
  
  int x = versioncheck(s,s2);
  
  if(x == 1)  
	  printf("version2");
  else if( x <0)
	  printf("version1");
  else
	  printf("equal");
}
```

| INPUT                | OUTPUT   |
| -------------------- | -------- |
| 2.05.001<br>2.02.005 | version1 |

---
***6. PANAGRAM***

```C
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int main(){
  char s[100];
  fgets(s,sizeof(s),stdin);
  s[strcspn(s,"\n")]='\0';
  
  int hash[26] = {0};
  int x = strlen(s);
  
  for(int i=0;i<x;i++){
    if(isalpha(s[i]))    hash[tolower(s[i]) - 'a']++;
  }
  
  for(int i=0;i<26;i++){
    if(hash[i] == 0){
      printf("not a panagram");
      return 0 ;
    }
  }
  printf("panagram");
}
```
---
***7.ANAGRAM***
*7.1 USING HASH*

```C
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int is_anagram(char s[],char s2[]){
  int hash[26] = {0};
  
  int x1 = strlen(s);
  int x2 = strlen(s2);
  
  if(x1 != x2)  return 0;
  
  for(int i=0;i<x1;i++){
    hash[tolower(s[i])-'a']++;
    hash[tolower(s2[i])-'a']--;
  }
  for(int i=0;i<26;i++){
    if(hash[i]!=0)  return 0;
  }
  return 1;
}

int main(){
  char s[100];
  fgets(s,sizeof(s),stdin);
  s[strcspn(s,"\n")]='\0';
  
  char s2[100];
  fgets(s2,sizeof(s2),stdin);
  s2[strcspn(s2,"\n")]='\0';
  if(is_anagram(s,s2)){
    printf("anagram");
  }
  else{
    printf("not anagram");
  }
}
```
---
*7.2 WITHOUT HASH*

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
  
  int x1 = strlen(s);
  int x2 = strlen(s2);
  if(x1 != x2)
  {
    printf("not a anagram");
    return 0;
  }
  int not_found = 0,found;
  for(int i=0;i<x1;i++){
    found =0;
    for(int j=0;j<x1;j++){
      if(s[i] == s2[j]){
	        found = 1;
	        break;
       }
    }
    if(found == 0){
	    not_found = 1;
	    break;
    }
  }
  if(not_found == 0)  
	  printf("anagram");
  else 
	  printf("not  a anagram");
```
---
***8. ISOMORPHIC***

```C
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int is_ismorphic(char * s,char * t){
  int map1[256]={0};
  int map2[256] = {0};
  
  int x = strlen(s);
  
  if(x!=strlen(t))  return 0;
  
  for(int i=0;i<x;i++){
    if(map1[s[i]] != map2[t[i]])  return 0;
    
    map1[s[i]] = i+1;
    map2[t[i]] = i+1;
  }
  return 1;
}


int main(){
  char s[100];
  fgets(s,sizeof(s),stdin);
  s[strcspn(s,"\n")]='\0';
  
  char s2[100];
  fgets(s2,sizeof(s2),stdin);
  s2[strcspn(s2,"\n")]='\0';
  
  if(is_ismorphic(s,s2)){
    printf("ismorphic");
  }
  else  printf("not");
}
```
---
***9. RAILWAY TIME***

```C
#include <stdio.h>
#include <string.h>

int main() {
  
  char str[100];
  fgets(str,sizeof(str),stdin);
  
  if(strlen(str)!=8){
    printf("invalid");
    return 0;
  }
  
  if(str[0]=='0' ||str[0]=='1'){
    if(!(str[1]>='0' && str[1]<='9')){
      printf("invalid");
      return 0;
    }
  }
  
  else if(str[0]=='2'){
    if(!(str[1]>='0' && str[1]<'4')){
      printf("invalid");
      return 0;
    }
  }
  else{
    printf("invalid");
    return 0;
  }
  
  if(str[3]>='0' && str[3] <'6'){
    if(!(str[4]>='0' && str[4]<='9')){
      printf("invalid");
      return 0;
    }
  }
  else{
    printf("invalid");
    return 0;
  }
  
  if(str[6]>='0' && str[6] <'6'){
    if(!(str[7]>='0' && str[7]<='9')){
      printf("invalid");
      return 0;
    }
  }
  else{
    printf("invalid");
    return 0;
  }
  printf("hours:%c%c minutes:%c%c   seconds:%c%c",str[0],str[1],str[3],str[4],str[6],str[7]); 
}
```

| S.NO |  INPUT   |             OUPUT              |
| ---- | :------: | :----------------------------: |
| 1    | 12:25:90 |            invalid             |
| 2    | 12:25:50 | hours:12 minutes:25 seconds:50 |

---
