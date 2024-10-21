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

# Cryptography---19CS412-classical-techqniques
# EX: 4 Vigenere Cipher
# DATE: 
Vigenere Cipher using with different key values

# AIM:

To develop a simple C program to implement Vigenere Cipher.

## ALGORITHM:

1. Choose the Keyword. 
2. Align Plaintext with Keyword.
3. Convert Letters to Numbers.
4. Shift Plaintext by Corresponding Keyword Character. 
5. Convert the Ciphertext Numbers Back to Letters. 

## PROGRAM:
DEVELOPED BY : V. POOJAA SREE
REGISTER NO : 212223040147

```
#include <stdio.h>  
#include<stdlib.h>  
#include <ctype.h>  
#include <string.h>  
void encipher();  
void decipher();  
void main()  
{  
int choice;  
while(1)  
{  
printf("\n1. Encrypt Text");  
printf("\t2. Decrypt Text");  
printf("\t3. Exit");  
printf("\n\nEnter Your Choice : ");  
scanf("%d",&choice);  
if(choice == 3)  
exit(0);  
else if(choice == 1)  
encipher();  
else if(choice == 2)  
decipher();  
else  
printf("Please Enter Valid Option.");  
}  
}  
void encipher()  
{  
unsigned int i,j;  
char input[50],key[10];  
printf("\n\nEnter Plain Text: ");  
scanf("%s",input);  
printf("\nEnter Key Value: ");  
scanf("%s",key);  
printf("\nResultant Cipher Text: ");  
for(i=0,j=0;i<strlen(input);i++,j++)  
{  
if(j>=strlen(key))  
{  
j=0;  
}  
printf("%c",65+(((toupper(input[i])-65)+(toupper(key[j])-65))%26));  
}  
}  
void decipher()  
{  
unsigned int i,j;  
char input[50],key[10];  
int value;  
printf("\n\nEnter Cipher Text: ");  
scanf("%s",input);  
printf("\n\nEnter the key value: ");  
scanf("%s",key);  
for(i=0,j=0;i<strlen(input);i++,j++)  
{  
if(j>=strlen(key))  
{  
j=0;  
}  
value = (toupper(input[i])-64)-(toupper(key[j])-64);  
if( value < 0)  
{  
value = value * -1;  
}  
printf("%c",65 + (value % 26));  
}  
}  

```

## OUTPUT:

![op](https://github.com/user-attachments/assets/bccd4432-d218-4261-92dd-b38d96727442)

## RESULT:
The program is executed and verified successfully.

-----------------------------------------------------------------------


# Cryptography---19CS412-classical-techqniques
# EX: 5 Rail Fence Cipher
# DATE: 

# AIM:

To develop a simple C program to implement Rail Fence Cipher.

## ALGORITHM:

1. Choose the Number of Rails.
2. Write the Plaintext in a Zigzag Pattern. 
3. Read Each Rail Row-by-Row.
4. Combine the Letters from All Rails. 
5. Output the Ciphertext. 


## PROGRAM:
DEVELOPED BY : V. POOJAA SREE
REGISTER NO : 212223040147

```
#include<stdio.h>
#include<string.h>

int main()
{
    int i, j, k, l;
    char a[20], c[20], d[20];

    printf("\n\t\t RAIL FENCE TECHNIQUE");
    printf("\n\nEnter the input string : ");
    l = strlen(a);

    for(i = 0, j = 0; i < l; i++)
    {
        if(i % 2 == 0)
            c[j++] = a[i];
    }
    for(i = 0; i < l; i++)
    {
        if(i % 2 == 1)
            c[j++] = a[i];
    }
    c[j] = '\0';

    printf("\nCipher text after applying rail fence : ");
    printf("%s", c);

    if(l % 2 == 0)
        k = l / 2;
    else
        k = (l / 2) + 1;

    for(i = 0, j = 0; i < k; i++)
    {
        d[j] = c[i];
        j = j + 2;
    }
    for(i = k, j = 1; i < l; i++)
    {
        d[j] = c[i];
        j = j + 2;
    }
    d[l] = '\0';

    printf("\nText after decryption : ");
    printf("%s", d);

    return 0;
}

```


## OUTPUT:

![op](https://github.com/user-attachments/assets/bd8bca9c-7f9d-41b3-b203-e5dddc3dc95c)


## RESULT:
The program is executed and verifed successfully.
