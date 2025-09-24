# EX-8-ADVANCED-ENCRYPTION-STANDARD ALGORITHM
# Aim:
To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

# ALGORITHM:
Step 1: Get the input plaintext and key from the user. 

Step 2. Treat the plaintext as a single block of characters. 

Step 3. Perform XOR operation between each character of plaintext and the corresponding character of the 
key (key repeats if shorter). 

Step 4. Store the XOR result as the ciphertext. 

Step 5. Display the ciphertext in ASCII format. 

Step 6. Perform XOR operation again between the ciphertext and the same key to decrypt. 

Step 7. Store and display the original message as the decrypted text.

# PROGRAM:
```
#include <stdio.h>
#include <string.h>
void simpleAESEncrypt(char *plaintext, char *key, char *ciphertext) 
{
    int i;
    int keyLength = strlen(key);
    for (i = 0; i < strlen(plaintext); i++) 
    {
        ciphertext[i] = plaintext[i] ^ key[i % keyLength];
    }
    ciphertext[i] = '\0';  // Null terminate
}
void simpleAESDecrypt(char *ciphertext, char *key, char *decryptedText) 
{
    int i;
    int keyLength = strlen(key);
    for (i = 0; i < strlen(ciphertext); i++) 
    {
        decryptedText[i] = ciphertext[i] ^ key[i % keyLength];
    }
    decryptedText[i] = '\0';  // Null terminate
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

    // Encrypt
    simpleAESEncrypt(plaintext, key, ciphertext);
    printASCII(ciphertext);

    // Decrypt
    simpleAESDecrypt(ciphertext, key, decryptedText);
    printf("Decrypted Message: %s\n", decryptedText);

    return 0;
}

```
# OUTPUT:

<img width="1120" height="559" alt="Screenshot 2025-09-24 083954" src="https://github.com/user-attachments/assets/0c18197d-c212-4469-8c13-3a8ef12d75a9" />

# RESULT:

Hence, Advanced Encryption Standard (AES) Algorithm for a practical application like URL 
Encryption is done successfully.
