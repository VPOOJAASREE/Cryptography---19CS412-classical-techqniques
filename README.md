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


--------------------------------------------------

# EX-7 Implement DES Encryption and Decryption
# DATE:

## AIM:
   Implementation of Pseudorandom Number Generation Using Standard library.

## ALGORITHM: 
1. Get the input and convert it as block cipher.
2. The plain text is initially permuted and split into 2 equal halves.
3. It undergoes 16 rounds of encryption.
4. These 2 halves are finally rejoined to give cipher text.
5. The same happens in decryption process but in an inverse manner

## PROGRAM: 

DEVELOPED BY: V. POOJAA SREE

REGISTER NO.: 212223040147

```
#include <stdio.h>
#include <string.h>

// Function to perform a simple XOR-based encryption
void encrypt(char *message, char *key, char *encryptedMessage, int messageLength) {
    int keyLength = strlen(key);

    for (int i = 0; i < messageLength; i++) {
        // Encrypt by XORing message byte with key byte
        encryptedMessage[i] = message[i] ^ key[i % keyLength];
    }
    encryptedMessage[messageLength] = '\0';  // Null-terminate the encrypted message
}

// Function to perform decryption (XOR again with the same key)
void decrypt(char *encryptedMessage, char *key, char *decryptedMessage, int messageLength) {
    int keyLength = strlen(key);

    for (int i = 0; i < messageLength; i++) {
        // Decrypt by XORing encrypted byte with key byte
        decryptedMessage[i] = encryptedMessage[i] ^ key[i % keyLength];
    }
    decryptedMessage[messageLength] = '\0';  // Null-terminate the decrypted message
}

int main() {
    char message[100];
    char key[100];
    
    printf("\n      *****Simulation of DES encryption and decryption*****\n\n");
    // Get user input for the message
    printf("Enter the message to encrypt: ");
    fgets(message, sizeof(message), stdin);
    message[strcspn(message, "\n")] = '\0';  // Remove newline character if present

    // Get user input for the key
    printf("Enter the encryption key: ");
    fgets(key, sizeof(key), stdin);
    key[strcspn(key, "\n")] = '\0';  // Remove newline character if present

    int messageLength = strlen(message);
    
    // Buffers to hold encrypted and decrypted messages
    char encryptedMessage[100];
    char decryptedMessage[100];
    
    // Encrypt the message
    encrypt(message, key, encryptedMessage, messageLength);
    printf("Original Message: %s\n", message);
    printf("Encrypted Message: ");
    
    // Print encrypted message in hex format
    for (int i = 0; i < messageLength; i++) {
        printf("%02X ", (unsigned char)encryptedMessage[i]);
    }
    printf("\n");
    
    // Decrypt the message
    decrypt(encryptedMessage, key, decryptedMessage, messageLength);
    printf("Decrypted Message: %s\n", decryptedMessage);
    
    return 0;
}

```

## OUTPUT:

![op](https://github.com/user-attachments/assets/9f07be16-b921-4493-9a62-1c1e13490bb7)


## RESULT: 
The program is executed and verified successfully.


-----------------------------------------------------

# EX-8 ADVANCED-ENCRYPTION-STANDARD DES-ALGORITHM 
# DATE:

## AIM:

  To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

## ALGORITHM: 

1. AES is based on a design principle known as a         
     substitution–permutation.
 2. AES does not use a Feistel network like DES, it uses variant of   
     Rijndael. 
3. It has a fixed block size of 128 bits, and a key size of 128, 192, or 256     
    bits.
 4. AES operates on a 4 × 4 column-major order array of bytes, termed 
     the state.

## PROGRAM: 

DEVELOPED BY: V. POOJAA SREE

REGISTER NO.: 212223040147

```
#include <stdio.h>
#include <string.h>

void simpleAESEncrypt(char *plaintext, char *key, char *ciphertext)
{
    int i;
    for (i = 0; i < strlen(plaintext); i++) 
    {
        ciphertext[i] = plaintext[i] ^ key[i % strlen(key)]; 
    }
    ciphertext[i] = '\0'; 
}

void simpleAESDecrypt(char *ciphertext, char *key, char *decryptedText)
{
    int i;
    for (i = 0; i < strlen(ciphertext); i++) 
    {
        decryptedText[i] = ciphertext[i] ^ key[i % strlen(key)]; 
    }
    decryptedText[i] = '\0'; 
}

void printASCII(char *ciphertext) 
{
    printf("Encrypted Message (ASCII values): ");
    for (int i = 0; i < strlen(ciphertext); i++) 
    {
        printf("%d ", (unsigned char)ciphertext[i]); 
    }
    printf("\n");
}

int main() 
{
    char plaintext[100], key[100], ciphertext[100], decryptedText[100];

    printf("Enter the plaintext: ");
    scanf("%s", plaintext);

    printf("Enter the key: ");
    scanf("%s", key);

    simpleAESEncrypt(plaintext, key, ciphertext);
    printASCII(ciphertext);  

    simpleAESDecrypt(ciphertext, key, decryptedText);
    printf("Decrypted Message: %s\n", decryptedText);

    return 0;
}

```

## OUTPUT:

![op](https://github.com/user-attachments/assets/20d707d1-ef9e-4661-a2a3-be42d0640cd8)

## RESULT: 

Hence,to use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption is done successfully.

------------------------------------------------

# EX-9 SIMULATION OF RSA ALGORITHM
# DATE:

## AIM:
   To implement encryption and decryption using RSA algorithm.

## ALGORITHM: 
1. Select 2 prime numbers p and q.
2.	Calculate n and pi(n).
3. Choose small number e.
4. Calculate d.
5. Perform encryption and decryption and get the outputs correspondingly.


## PROGRAM: 

DEVELOPED BY: V. POOJAA SREE

REGISTER NO.: 212223040147

```
#include <stdio.h>
#include <math.h>

// Function to calculate greatest common divisor (GCD)
int gcd(int a, int b) {
    while (b != 0) {
        int temp = b;
        b = a % b;
        a = temp;
    }
    return a;
}

// Function to calculate (base^exp) % mod using modular exponentiation
int mod_exp(int base, int exp, int mod) {
    int result = 1;
    base = base % mod;
    
    while (exp > 0) {
        if (exp % 2 == 1) {
            result = (result * base) % mod;
        }
        exp = exp >> 1;  // exp = exp / 2
        base = (base * base) % mod;
    }
    
    return result;
}

// Function to find the modular inverse using Extended Euclidean Algorithm
int mod_inverse(int e, int phi_n) {
    int t = 0, new_t = 1;
    int r = phi_n, new_r = e;
    
    while (new_r != 0) {
        int quotient = r / new_r;
        int temp_t = t;
        t = new_t;
        new_t = temp_t - quotient * new_t;
        
        int temp_r = r;
        r = new_r;
        new_r = temp_r - quotient * new_r;
    }
    
    if (r > 1) return -1;  // No inverse
    if (t < 0) t += phi_n;
    
    return t;
}

int main() {
    int p, q, n, phi_n, e, d;
    int message, encrypted_message, decrypted_message;
    
    printf("\n            *****Simulation of RSA Encryption and Decryption*****\n\n");
    // Get two prime numbers from the user
    printf("Enter a prime number (p): ");
    scanf("%d", &p);
    printf("Enter another prime number (q): ");
    scanf("%d", &q);
    
    // Calculate n and phi(n)
    n = p * q;
    phi_n = (p - 1) * (q - 1);
    
    // Choose the public key exponent e such that 1 < e < phi_n and gcd(e, phi_n) = 1
    do {
        printf("Enter a value for public key exponent (e) such that 1 < e < %d: ", phi_n);
        scanf("%d", &e);
    } while (gcd(e, phi_n) != 1);
    
    // Calculate the private key exponent d (modular inverse of e)
    d = mod_inverse(e, phi_n);
    if (d == -1) {
        printf("Modular inverse does not exist for the given 'e'. Exiting.\n");
        return 1;
    }
    
    printf("Public key: (n = %d, e = %d)\n", n, e);
    printf("Private key: (n = %d, d = %d)\n", n, d);
    
    // Get the message to encrypt
    printf("Enter the message to encrypt (as an integer): ");
    scanf("%d", &message);
    
    // Encrypt the message: ciphertext = (message^e) % n
    encrypted_message = mod_exp(message, e, n);
    printf("Encrypted message: %d\n", encrypted_message);
    
    // Decrypt the message: decrypted_message = (ciphertext^d) % n
    decrypted_message = mod_exp(encrypted_message, d, n);
    printf("Decrypted message: %d\n", decrypted_message);
    
    return 0;
}

```

## OUTPUT:

![op](https://github.com/user-attachments/assets/6e3eb6d4-2ac2-4a00-a8c7-ab2d3a11e7ab)


## RESULT: 
The program is executed and verified successfully.

