# Cryptography---19CS412-classical-techqniques
# EX:1 Caeser Cipher
## DATE: 

# AIM:

To encrypt and decrypt the given message by using Ceaser Cipher encryption algorithm.

## ALGORITHM:

1. Input the plaintext and key.
2. Loop through each character in the plaintext. 
3. Check if the character is a letter. 
4. Shift the character.
5. Print the resulting ciphertext. 


## PROGRAM:
DEVELOPED BY : V. POOJAA SREE
REGISTER NO : 212223040147

```
#include <stdio.h> 
#include <string.h> 
 
#include <ctype.h> 
void main() 
 
{ 
    char plain[10],cipher[10]; 
    int key,i,length; 
    int result; 
    printf("\n Enter the plain text:"); 
    scanf("%s", plain); 
    printf("\n Enter the key value:"); 
    scanf("%d", &key); 
    printf("\n \n \t PLAIN TEXt: %s", plain); 
    printf("\n \n \t ENCRYPTED TEXT:"); 
    for(i=0, length = strlen(plain); i<length; i++) 
    { 
         
        cipher[i]=plain[i] + key; 
        if (isupper(plain[i]) && (cipher[i] > 'Z')) 
        cipher[i] = cipher[i] - 26; 
        if (islower(plain[i]) && (cipher[i] > 'z')) 
        cipher[i] = cipher[i] - 26; 
        printf("%c", cipher[i]); 
 
    } 
    printf("\n \n \t AFTER DECRYPTION : "); 
    for(i=0;i<length;i++) 
    { 
         
        plain[i]=cipher[i]-key; 
        if(isupper(cipher[i])&&(plain[i]<'A')) 
        plain[i]=plain[i]+26; 
        if(islower(cipher[i])&&(plain[i]<'a')) 
        plain[i]=plain[i]+26; 
        printf("%c",plain[i]); 
    }    
}
```

## OUTPUT:
 ![EX1 output](https://github.com/user-attachments/assets/c297b6c9-3eb8-48b4-8b91-9eb1a91e6f7b)



## RESULT:
The program is executed and verified successfully.

---------------------------------

# Cryptography---19CS412-classical-techqniques
# EX: 2 PlayFair Cipher
## DATE: 

# AIM:

To implement a program to encrypt a plain text and decrypt a cipher text using play fair Cipher substitution technique.
 
## ALGORITHM:

1. Input the plaintext and the key 
2. Create the 5x5 cipher matrix 
3. Prepare the plaintext 
4. Encrypt the plaintext digraphs 
5. Output the ciphertext

## PROGRAM:
DEVELOPED BY : V. POOJAA SREE
REGISTER NO : 212223040147

```
#include<stdio.h> 
#include<string.h> 
int main() 
{ 
    unsigned int a[3][3]={{6,24,1},{13,16,10},{20,17,15}}; 
    unsigned int b[3][3]={{8,5,10},{21,8,21},{21,12,8}}; 
    int i,j, t=0; 
    unsigned int c[20],d[20]; 
    char msg[20]; 
    printf("Enter plain text: "); 
    scanf("%s",msg); 
    for(i=0;i<strlen(msg);i++) 
    { 
        c[i]=msg[i]-65; 
        printf("%d ",c[i]); 
    } 
    for(i=0;i<3;i++) 
    { 
        t=0; 
        for(j=0;j<3;j++) 
        { 
            t=t+(a[i][j]*c[j]); 
        } 
        d[i]=t%26; 
    } 
    printf("\nEncrypted Cipher Text :"); 
    for(i=0;i<3;i++) 
    printf(" %c",d[i]+65); 
    for(i=0;i<3;i++) 
    { 
        t=0; 
        for(j=0;j<3;j++) 
        { 
            t=t+(b[i][j]*d[j]); 
        } 
        c[i]=t%26; 
    } 
    printf("\nDecrypted Cipher Text :"); 
    for(i=0;i<3;i++) 
    printf(" %c",c[i]+65); 
    return 0; 
} 

```

## OUTPUT:
![Ex2 output](https://github.com/user-attachments/assets/ac4599d2-24a0-4def-92d7-276811fe9558)


## RESULT:
The program is executed and verified successfully.

---------------------------

# Cryptography---19CS412-classical-techqniques
# Ex: 3 Hill Cipher
# DATE:

# AIM:

To develop a simple C program to implement Hill Cipher.

## ALGORITHM:

1. Key Matrix Selection  
2. Convert Plaintext into Vector  
3. Matrix Multiplication  
4. Convert Vector to Ciphertext  
5. Output Ciphertext 

## PROGRAM:
DEVELOPED BY : V. POOJAA SREE
REGISTER NO : 212223040147

```
#include<stdio.h> 
#include<string.h> 
int main() 
{ 
unsigned int a[3][3]={{6,24,1},{13,16,10},{20,17,15}}; 
unsigned int b[3][3]={{8,5,10},{21,8,21},{21,12,8}}; 
int i,j, t=0; 
unsigned int c[20],d[20]; 
char msg[20]; 
printf("Enter plain text:"); 
scanf("%s",msg); 
for(i=0;i<strlen(msg);i++) 
{ c[i]=msg[i]-65; 
printf("%d ",c[i]); 
} 
for(i=0;i<3;i++) 
{ t=0; 
for(j=0;j<3;j++) 
{ 
t=t+(a[i][j]*c[j]); 
} 
d[i]=t%26; 
} 
printf("\nEncrypted Cipher Text :"); 
for(i=0;i<3;i++) 
printf(" %c",d[i]+65); 
for(i=0;i<3;i++) 
{ 
t=0; 
for(j=0;j<3;j++) 
{ 
t=t+(b[i][j]*d[j]); 
} 
c[i]=t%26; 
} 
printf("\nDecrypted Cipher Text :"); 
for(i=0;i<3;i++) 
printf(" %c",c[i]+65); 
return 0; 
}    

```


## OUTPUT:

![Ex3 Output](https://github.com/user-attachments/assets/af858146-339f-4550-b7c3-f16aa9b20919)


## RESULT:
The program is executed and verified successfully.

-------------------------------------------------

# Vigenere Cipher
Vigenere Cipher using with different key values

# AIM:

To develop a simple C program to implement Vigenere Cipher.

## DESIGN STEPS:

### Step 1:

Design of Vigenere Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 
ALGORITHM DESCRIPTION:
The Vigenere cipher is a method of encrypting alphabetic text by using a series of different Caesar ciphers based on the letters of a keyword. It is a simple form of polyalphabetic substitution.To encrypt, a table of alphabets can be used, termed a Vigenere square, or Vigenere table. It consists of the alphabet written out 26 times in different rows, each alphabet shifted cyclically to the left compared to the previous alphabet, corresponding to the 26 possible Caesar ciphers. At different points in the encryption process, the cipher uses a different alphabet from one of the rows used. The alphabet at each point depends on a repeating keyword.



## PROGRAM:
PROGRAM:
#include<stdio.h> #include<string.h>
//FunctiontoperformVigenereencryption voidvigenereEncrypt(char*text,constchar*key){ inttextLen= strlen(text);
intkeyLen=strlen(key); for(inti =0;i< textLen;i++){ charc =text[i]; if(c>='A'&&c<='Z'){
//Encryptuppercaseletters
text[i]=((c-'A'+key[i%keyLen]-'A')%26)+'A';
}else if(c>='a'&&c<='z'){
//Encryptlowercaseletters
text[i]=((c-'a'+key[i%keyLen]-'A')%26)+'a';
}
}
}
//FunctiontoperformVigeneredecryption voidvigenereDecrypt(char*text,constchar*key){ inttextLen= strlen(text);
intkeyLen=strlen(key);

for(inti =0;i< textLen;i++){ charc =text[i]; if(c>='A'&&c<='Z'){
//Decryptuppercaseletters
 
text[i]=((c-'A'-(key[i% keyLen]-'A') +26) %26)+ 'A';
}else if(c>='a'&&c<='z'){
//Decryptlowercaseletters
text[i]=((c-'a'-(key[i% keyLen]-'A') +26) %26)+ 'a';
}
}
}
intmain(){
constchar *key="KEY";//Replacewithyourdesired key
char message[]= "Thisisasecretmessage.";//Replace withyourmessage
//Encrypt themessage vigenereEncrypt(message,key); printf("EncryptedMessage:%s\n",message);
//Decrypt themessage backtotheoriginal vigenereDecrypt(message,key); printf("DecryptedMessage:%s\n",message); Return 0;

## OUTPUT:
OUTPUT :

Simulating Vigenere Cipher


Input Message : SecurityLaboratory
Encrypted Message : NMIYEMKCNIQVVROWXC Decrypted Message : SECURITYLABORATORY
## RESULT:
The program is executed successfully

-----------------------------------------------------------------------

# Rail Fence Cipher
Rail Fence Cipher using with different key values

# AIM:

To develop a simple C program to implement Rail Fence Cipher.

## DESIGN STEPS:

### Step 1:

Design of Rail Fence Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 
ALGORITHM DESCRIPTION:
In the rail fence cipher, the plaintext is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

## PROGRAM:

PROGRAM:
#include<stdio.h> #include<string.h> #include<stdlib.h> main()
{
int i,j,len,rails,count,code[100][1000]; char str[1000];
printf("Enter a Secret Message\n"); gets(str);
len=strlen(str);
printf("Enter number of rails\n"); scanf("%d",&rails); for(i=0;i<rails;i++)
{
for(j=0;j<len;j++)
{
code[i][j]=0;
}
}
count=0; j=0;
while(j<len)
{
if(count%2==0)
{
for(i=0;i<rails;i++)
{
//strcpy(code[i][j],str[j]);
code[i][j]=(int)str[j]; j++;
}

}
else
{
 
for(i=rails-2;i>0;i--)
{
code[i][j]=(int)str[j]; j++;
}
}

count++;
}

for(i=0;i<rails;i++)
{
for(j=0;j<len;j++)
{
if(code[i][j]!=0) printf("%c",code[i][j]);
}
}
printf("\n");
}
## OUTPUT:
OUTPUT:
Enter a Secret Message wearediscovered
Enter number of rails 2
waeicvrderdsoee
## RESULT:
The program is executed successfully
