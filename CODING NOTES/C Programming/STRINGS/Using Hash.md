***1. HASHING BASIC***

```C
#include <stdio.h>
#include <string.h>

int main()
{
  char str[100];
  fgets(str,sizeof(str),stdin);
    
  char hash[256] = {0};
  for(int i=0;i<strlen(str);i++){
      hash[str[i]]++;
    }
    
  for(int i=0;i<256;i++){
      if(hash[i]>0)
        printf("%c %d\n",i,hash[i]);
    }
  return 0;
}
```
---
***2. PANAGRAM***

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
***3.ANAGRAM***

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
***4. ISOMORPHIC***

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
***5. FIRST OCCURANCE OF A CHARACTER***

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
