### EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER

### AIM:

To implement the simple substitution technique named Caesar cipher using C language.

### ALGORITHM:

STEP-1: Read the plain text from the user.

STEP-2: Read the key value from the user.

STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.

STEP-4: Else subtract the key from the plain text.

STEP-5: Display the cipher text obtained above.


### PROGRAM :-
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>
int main() {
    char plain[100], cipher[100];
    int key, i, length;
    printf("Enter the plain text: ");
    scanf("%99s", plain);  // Limit input to 99 characters
    printf("Enter the key value: ");
    scanf("%d", &key);
    printf("\nPLAIN TEXT: %s", plain);
    printf("\nENCRYPTED TEXT: ");
    length = strlen(plain);
    for (i = 0; i < length; i++) {
        cipher[i] = plain[i] + key;
        if (isupper(plain[i]) && cipher[i] > 'Z')
            cipher[i] -= 26;
        else if (islower(plain[i]) && cipher[i] > 'z')
            cipher[i] -= 26;
        printf("%c", cipher[i]);
    }
    cipher[length] = '\0';  // Null-terminate the cipher text
    printf("\nDECRYPTED TEXT: ");
    for (i = 0; i < length; i++) {
        plain[i] = cipher[i] - key;
        if (isupper(cipher[i]) && plain[i] < 'A')
            plain[i] += 26;
        else if (islower(cipher[i]) && plain[i] < 'a')
            plain[i] += 26;
        printf("%c", plain[i]);
    }
    printf("\n");
    return 0;
}
```

### OUTPUT :-
![Uploading image.png…]()


### Result:
Hence the output is verified sucessfully
