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

--------------------------------------------------



# EX-10 SIMULATION OF DIFFIE HELLMAN ALGORITHM
# DATE:

## AIM: 
To implement key exchange between users using Diffie Hellman algorithm.
   
## ALGORITHM: 
1.	Get the input for prime number p.
2. Calculate the primitive root of p that is g.
3. Calculate private keys for both users using p and g values.
4. Similarly, secret keys for both users are calculated.

## PROGRAM: 

DEVELOPED BY: V. POOJAA SREE

REGISTER NO.: 212223040147

```
#include <math.h>
#include <stdio.h>
// Power function to return value of a ^ b mod P
long long int power(long long int a, long long int b,
long long int P)
{
    if (b == 1)
    return a;
    else
    return (((long long int)pow(a, b)) % P);
}
// Driver program
int main()
{
    long long int P, G, x, a, y, b, ka, kb;
    // Both the persons will be agreed upon the
    // public keys G and P
    printf("\n                  *****Diffie-Hellman Key Exchange algorithm*****\n\n");
    printf("\n\nEnter the value of P: ");
    scanf("%lld",&P); // A prime number P is taken
    printf("The value of P: %lld\n", P);
    printf("Enter the value of G (Primitive root of P): ");
    scanf("%lld",&G); // A primitive root for P, G is taken
    printf("The value of G: %lld\n\n", G);
    // Alice will choose the private key a
    a = 4; // a is the chosen private key
    printf("The private key a for Alice : %lld\n", a);
    x = power(G, a, P); // gets the generated key
    // Bob will choose the private key b
    b = 3; // b is the chosen private key
    printf("The private key b for Bob : %lld\n\n", b);
    y = power(G, b, P); // gets the generated key
    // Generating the secret key after the exchange
    // of keys
    ka = power(y, a, P); // Secret key for Alice
    kb = power(x, b, P); // Secret key for Bob
    printf("Secret key for the Alice is : %lld\n", ka);
    printf("Secret Key for the Bob is : %lld\n", kb);
    return 0;
}

```

## OUTPUT:

![op](https://github.com/user-attachments/assets/603f0e52-3a28-4447-946b-e4c804398935)

## RESULT: 
The program is executed and verified successfully.

-------------------------------------------------------------


# EX-11 ELLIPTIC CURVE CRYPTOGRAPHY
# DATE:

## AIM: 
 To perform key exchange using the Elliptic Curve Cryptography (ECC) method.
   
## ALGORITHM: 
1. Choose a large prime number p and an elliptic curve defined by the equation y^2 = x^3 +
 ax+b mod p along with a base point G on the curve.
2. Alice and Bob choose private keys.
3. Compute public keys: public_key = private_key* G (point multiplication).
4. Exchange public keys.
5. Compute the shared secret: shared_secret = private_key* public_key_received

## PROGRAM: 

DEVELOPED BY: V. POOJAA SREE

REGISTER NO.: 212223040147

```
 #include <stdio.h>
 // A simple structure to represent points on the elliptic curve
 typedef struct {
 long long int x, y;
 } Point;
 // Function to compute modular inverse (using Extended Euclidean Algorithm)
 long long int modInverse(long long int a, long long int m) {
 long long int m0 = m, t, q;
 long long int x0 = 0, x1 = 1;
 if (m == 1) return 0;
 while (a > 1) {
 q =a/m;
 t = m;
 m=a%m;
 a =t;
 t = x0;
 x0 = x1- q * x0;
 x1 = t;
 }
 if (x1 < 0) x1 += m;
 return x1;
 }
 // Function to perform point addition on elliptic curves
 Point pointAddition(Point P, Point Q, long long int a, long long int p) {
 Point R;
long long int lambda;
 if (P.x == Q.x && P.y == Q.y) { // Point doubling
 lambda = (3 * P.x * P.x + a) * modInverse(2 * P.y, p) % p;
 } else { // Point addition
 lambda = (Q.y- P.y) * modInverse(Q.x- P.x, p) % p;
 }
 R.x = (lambda * lambda- P.x- Q.x) % p;
 R.y = (lambda * (P.x- R.x)- P.y) % p;
 // Ensure values are positive
 if (R.x < 0) R.x += p;
 if (R.y < 0) R.y += p;
 return R;
 }
 // Function to perform scalar multiplication (Elliptic Curve Point Multiplication)
 Point scalarMultiplication(Point P, long long int k, long long int a, long long int p) {
 Point result = P;
 k--; // Subtract 1 because we start with the base point
 while (k > 0) {
 result = pointAddition(result, P, a, p);
 k--;
 }
 return result;
 }
 int main() {
 long long int p, a, b, privateA, privateB;
 Point G, publicA, publicB, sharedSecretA, sharedSecretB;
 // Step 1: Input parameters of the elliptic curve
 printf("Enter the prime number (p): ");
 scanf("%lld", &p);
 printf("Enter the curve parameters (a and b) for equation y^2 = x^3 + ax + b: ");
 scanf("%lld %lld", &a, &b);
 printf("Enter the base point G (x and y): ");
 scanf("%lld %lld", &G.x, &G.y);
 // Step 2: Alice and Bob input private keys
 printf("Enter Alice's private key: ");
 scanf("%lld", &privateA);
printf("Enter Bob's private key: ");
 scanf("%lld", &privateB);
 publicA = scalarMultiplication(G, privateA, a, p); // Alice's public key
 publicB = scalarMultiplication(G, privateB, a, p); // Bob's public key
 printf("Alice's public key: (%lld, %lld)\n", publicA.x, publicA.y);
 printf("Bob's public key: (%lld, %lld)\n", publicB.x, publicB.y);
 sharedSecretA = scalarMultiplication(publicB, privateA, a, p); // Alice's shared
 sharedSecretB = scalarMultiplication(publicA, privateB, a, p); // Bob's shared secret
 printf("Shared secret computed by Alice: (%lld, %lld)\n", sharedSecretA.x,
 sharedSecretA.y);
 printf("Shared secret computed by Bob: (%lld, %lld)\n", sharedSecretB.x,
 sharedSecretB.y);
 if (sharedSecretA.x == sharedSecretB.x && sharedSecretA.y == sharedSecretB.y) {
 printf("Key exchange successful. Both shared secrets match!\n");
 } else {
 printf("Key exchange failed. Shared secrets do not match.\n");
 }
 return 0;
 }

```

## OUTPUT:

![op](https://github.com/user-attachments/assets/6f9098b8-e37c-4b81-9632-98da918c74c7)

## RESULT: 
The program is executed and verified successfully.

---------------------------

# EX-12 ELGAMAL ALGORITHM
# DATE:

## AIM: 
To encrypt and decrypt a message using the Elgamal encryption algorithm.
   
## ALGORITHM: 
1. Choose a large prime number p and a generator g of the multiplicative group of integers
 modulo p.
2. Alice chooses a private key and computes her public key as public_key =
 g^private_key mod p.
3. To encrypt a message, Bob chooses a random number k and
 computes a ciphertext pair (c1, c2).
4. To decrypt the message, Alice uses her private key and
 computes the original message.
5. The decrypted message is verified to be the same as the
 orginal.

## PROGRAM: 

DEVELOPED BY: V. POOJAA SREE

REGISTER NO.: 212223040147

```
 #include <stdio.h>
 // Function to perform modular exponentiation
 long long int modExp(long long int base, long long int exp, long long int mod) {
 long long int result = 1;
 while (exp > 0) {
 if (exp % 2 == 1) {
 result = (result * base) % mod;
 }
 base = (base * base) % mod;
 exp /= 2;
 }
 return result;
 }
 int main() {
 long long int p, g, privateKeyA, publickeyA;
 long long int k, message, c1, c2, decryptedMessage;
 // Input for prime number p and generator g
 printf("Enter a large prime number (p): ");
 scanf("%lld", &p);
 printf("Enter a generator (g): ");
 scanf("%lld", &g);
 // Alice's private key input
 printf("Enter Alice's private key: ");
 scanf("%lld", &privateKeyA);
 // Calculate Alice's public key
publickeyA = modExp(g, privateKeyA, p);
 printf("Alice's public key: %lld\n", publickeyA);
 // Step 4: Bob inputs the message to be encrypted and selects a random k
 printf("Enter the message to encrypt (as a number): ");
 scanf("%lld", &message);
 printf("Enter a random number k: ");
 scanf("%lld", &k);
 // Encryption process
 c1 = modExp(g, k, p);
 c2 = (message * modExp(publickeyA, k, p)) % p;
 printf("Encrypted message (c1, c2): (%lld, %lld)\n", c1, c2);
 return 0;
 }
```

## OUTPUT:

![op](https://github.com/user-attachments/assets/8bce10e9-2753-41e0-b560-3c83dcc590d8)


## RESULT: 
The program is executed and verified successfully.

---------------------------------------------------

# EX-13 MESSAGE AUTHENTICATION CODE(MAC)
# DATE:

## AIM: 
To generate and verify a Message Authentication Code (MAC) for ensuring the integrity and authenticity of a message using a simple XOR operation.
   
## ALGORITHM: 
1. Input the plaintext and key.
2. Loop through each character in the plaintext.
3. Check if the character is a letter.
4. Shift the character.
5. Print the resulting ciphertext.

## PROGRAM: 

DEVELOPED BY: V. POOJAA SREE

REGISTER NO.: 212223040147

```
#include <stdio.h>
#include <string.h>
#define MAC_SIZE 32

void computeMAC(const char *key, const char *message, char *mac) {
    int key_len = strlen(key);
    int msg_len = strlen(message);

    for (int i = 0; i < MAC_SIZE; i++) {
        mac[i] = key[i % key_len] ^ message[i % msg_len];
    }
    mac[MAC_SIZE] = '\0';
}

int main() {
    char key[100], message[100];
    char mac[MAC_SIZE + 1];
    char receivedMAC[MAC_SIZE + 1];

    printf("Enter the secret key: ");
    scanf("%s", key);

    printf("Enter the message: ");
    scanf("%s", message);

    computeMAC(key, message, mac);

    printf("Computed MAC (in hex): ");
    for (int i = 0; i < MAC_SIZE; i++) {
        printf("%02x", (unsigned char)mac[i]);
    }
    printf("\n");

    printf("Enter the received MAC (as hex): ");
    for (int i = 0; i < MAC_SIZE; i++) {
        scanf("%02hhx", &receivedMAC[i]);
    }

    if (memcmp(mac, receivedMAC, MAC_SIZE) == 0) {
        printf("MAC verification successful. Message is authentic.\n");
    } else {
        printf("MAC verification failed. Message is not authentic.\n");
    }

    return 0;
}


```

## OUTPUT:

![op](https://github.com/user-attachments/assets/f4980c24-8620-46d5-b5e9-bebcdd2c6df8)


## RESULT: 
The program is executed and verified successfully.

---------------------------------------------------------------

# EX-14 HASH
# DATE:

## AIM: 

To generate a simple hash of a given message using a custom hash function.
   
## ALGORITHM: 

1. Input a message from the user.
2. Use a basic custom hash function that applies simple operations like XOR and addition on the characters of the message.
3. Convert the resulting hash into a hexadecimal format.
4. Display the computed hash to the user.
5. Optionally verify the hash by recomputing it and comparing it with a received hash.

## PROGRAM: 

DEVELOPED BY: V. POOJAA SREE

REGISTER NO.: 212223040147

```
#include <stdio.h>
#include <string.h>

// Function to compute a simple hash using XOR and addition
void computeSimpleHash(const char *message, unsigned char *hash) {
    unsigned char temp = 0;
    for (int i = 0; message[i] != '\0'; i++) {
        temp ^= message[i];  // XOR each character
        temp += message[i];  // Add each character's value
    }
    *hash = temp;  // Store the result in the hash
}

int main() {
    char message[256];  // Buffer for the input message
    unsigned char hash; // Buffer for the hash (only 1 byte for simplicity)
    char receivedHash[3]; // Buffer for input of received hash (in hex format)

    // Step 1: Input the message
    printf("Enter the message: ");
    scanf("%s", message);

    // Step 2: Compute the simple hash
    computeSimpleHash(message, &hash);

    // Step 3: Display the computed hash in hexadecimal format
    printf("Computed Hash (in hex): %02x\n", hash);

    // Step 4: Input the received hash
    printf("Enter the received hash (in hex): ");
    scanf("%s", receivedHash);

    // Step 5: Convert received hash from hex string to an unsigned char
    unsigned int receivedHashValue;
    sscanf(receivedHash, "%02x", &receivedHashValue);

    // Step 6: Compare the computed hash with the received hash
    if (hash == receivedHashValue) {
        printf("Hash verification successful. Message is unchanged.\n");
    } else {
        printf("Hash verification failed. Message has been altered.\n");
    }

    return 0;
}

```

## OUTPUT:

![op](https://github.com/user-attachments/assets/4c8555b5-11dc-4a85-b663-13155496dee1)


## RESULT: 
The program is executed and verified successfully.

-------------------------------------------------------------

