
>***Functions needs to identify palindromes in user input. The function should be able to handle various types of input strings, including alphanumeric characters and punctuation.***


| S NO |            INPUT             | OUPUT |
| :--: | :--------------------------: | :---: |
|  1.  |            radar             | TRUE  |
|  2.  |            hello             | FALSE |
|  3.  | Was it a car or a cat I saw? | TRUE  |

```c
#include<stdio.h>
#include<string.h>
#include<stdlib.h>

int ispalindrome(char str[]){
  char copy[100];
  int i=0,j=0;
  
  while(str[i]!='\0'){
    if(isalnum(str[i])){
      copy[j++] = tolower(str[i]);
    }
    i++;
  }
  copy[j] = '\0';
  int start = 0;
  int end = j-1;
  
  while(start<end){
    if(copy[start] != copy[end])
      return 0;
    start++;
    end--;
  }
  return 1;
}


int main(){
  char str[100];
  fgets(str,sizeof(str),stdin);
  
  if(ispalindrome(str)){
    printf("TRUE");
  }
  else
    printf("FALSE");
}
```
