### ***1. LEFT ROTATE BY 'K' TERMS*** ###

```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>

void leftrotate(char *s,int k){
  int len = strlen(s);
  k = k%len;
  char temp[len];
  
  strncpy(temp,s+len-k,k);
  strncpy(temp+k,s,len-k);
  
  temp[len+1] = '\0';
  strcpy(s,temp);
}

int main(){
  char s[100];
  fgets(s,sizeof(s),stdin);
  s[strcspn(s,"\n")]='\0';
  int k;
  scanf("%d",&k);
  leftrotate(s,k);
  printf("%s",s);
}
```
---
### ***2. RIGHT ROTATE BY 'K' TERMS***###

```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>

void rightrotate(char *s,int k){
  int len = strlen(s);
  k = k%len;
  char temp[len];
  
  strncpy(temp,s+k,len-k);
  strncpy(temp+len-k,s,k);
  
  temp[len+1] = '\0';
  strcpy(s,temp);
}

int main(){
  char s[100];
  fgets(s,sizeof(s),stdin);
  s[strcspn(s,"\n")]='\0';
  int k;
  scanf("%d",&k);

  rightrotate(s,k);
  printf("%s",s);
  
}
```
---
### ***3. MATRIX OPERATIONS***###
*3.1 ROTATE 90 DEGREE | CLOCKWISE*

```c
#include<stdio.h>
#include<string.h>

int main(){
  char str[10][10];
  int n;
  scanf("%d",&n);
  for(int i=0;i<n;i++){
    for(int j=0;j<n;j++){
      scanf("%s",&str[i][j]);
    }
  }
  for(int i=0;i<n;i++){
    for(int j=n-1;j>=0;j--){
      printf("%c ",str[j][i]);
    }
    printf("\n");
  }
}
```

| INPUT                        | OUTPUT                    |
| ---------------------------- | ------------------------- |
| 3<br>1 2 3<br>4 5 6<br>7 8 9 | 7 4 1 <br>8 5 2 <br>9 6 3 |

---
*3.2 TRANSPORSE*

```c
#include<stdio.h>
#include<string.h>

int main(){
  char str[10][10];
  int n;
  scanf("%d",&n);
  for(int i=0;i<n;i++){
    for(int j=0;j<n;j++){
      scanf("%s",&str[i][j]);
    }
  }
  for(int i=0;i<n;i++){
    for(int j=0;j<n;j++){
      printf("%c ",str[j][i]);
    }
    printf("\n");
  }
}
```

| INPUT                        | OUTPUT                    |
| ---------------------------- | ------------------------- |
| 3<br>1 2 3<br>4 5 6<br>7 8 9 | 1 4 7 <br>2 5 8 <br>3 6 9 |

---
*3.3 ROTATE -90 DEGREE | ANTI-CLOCKWISE*

```c
#include<stdio.h>
#include<string.h>

int main(){
  char str[10][10];
  int n;
  scanf("%d",&n);
  for(int i=0;i<n;i++){
    for(int j=0;j<n;j++){
      scanf("%s",&str[i][j]);
    }
  }
  for(int i=n-1;i>=0;i--){
    for(int j=0;j<n;j++){
      printf("%c ",str[j][i]);
    }
    printf("\n");
  }
}
```

| INPUT                        | OUTPUT                    |
| ---------------------------- | ------------------------- |
| 3<br>1 2 3<br>4 5 6<br>7 8 9 | 3 6 9 <br>2 5 8 <br>1 4 7 |

---
