# Ex-4 Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE
## NAME: PRIYADHARSHINI P
## REGISTER NUMBER: 212224040252
## DATE: 03-02-2026
## AIM:

 To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM:
```
#include <stdio.h>
#include <string.h>

int main(){
    char p[100],c[100],d[100]; int k,i,r=0,dir=1,len,idx=0;
    scanf("%s%d",p,&k); len=strlen(p);
    char rail[k][len]; memset(rail,'\n',sizeof(rail));

    for(i=0;i<len;i++){ rail[r][i]=p[i]; r+=dir; if(r==0||r==k-1) dir=-dir; }
    for(r=0;r<k;r++) for(i=0;i<len;i++) if(rail[r][i]!='\n') c[idx++]=rail[r][i];
    c[idx]='\0'; printf("Enc:%s",c);

    memset(rail,'\n',sizeof(rail)); idx=0; r=0; dir=1;
    for(i=0;i<len;i++){ rail[r][i]='*'; r+=dir; if(r==0||r==k-1) dir=-dir; }
    for(r=0;r<k;r++) for(i=0;i<len;i++) if(rail[r][i]=='*') rail[r][i]=c[idx++];
    r=0; dir=1;
    for(i=0;i<len;i++){ d[i]=rail[r][i]; r+=dir; if(r==0||r==k-1) dir=-dir; }
    d[len]='\0'; printf("\nDec:%s",d);
}
```
# OUTPUT:
<img width="1327" height="758" alt="image" src="https://github.com/user-attachments/assets/0bf91a36-86d8-4a0b-958b-7c9b1ca467cc" />


# RESULT:
The program is executed successfully.
