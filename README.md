# EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER
## DATE: 23-10-2026
## AIM:
To implement the simple substitution technique named Caesar cipher using C language.

## ALOGORITHM:

STEP-1: Read the plain text from the user.

STEP-2: Read the key value from the user.

STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.

STEP-4: Else subtract the key from the plain text.

STEP-5: Display the cipher text obtained above.

## DEVELOPED BY 
### HARI VARSHAN V.

### 212224230092

## PROGRAM:
```

#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main()
{
    char p[100], c[100];
    int i, k, n;

    printf("Enter plain text: ");
    fgets(p, sizeof(p), stdin);
    p[strcspn(p, "\n")] = '\0';

    printf("Enter key: ");
    scanf("%d", &k);

    k = (k % 26 + 26) % 26;
    n = strlen(p);

    for (i = 0; i < n; i++)
        c[i] = isupper((unsigned char)p[i])
        ? (p[i] - 'A' + k) % 26 + 'A'
        : islower((unsigned char)p[i])
        ? (p[i] - 'a' + k) % 26 + 'a'
        : p[i];

    c[n] = '\0';

    printf("\nPLAIN TEXT: %s", p);
    printf("\nENCRYPTED TEXT: %s", c);

    for (i = 0; i < n; i++)
        p[i] = isupper((unsigned char)c[i])
        ? (c[i] - 'A' - k + 26) % 26 + 'A'
        : islower((unsigned char)c[i])
        ? (c[i] - 'a' - k + 26) % 26 + 'a'
        : c[i];

    p[n] = '\0';
    printf("\nDECRYPTED TEXT: %s\n", p);

    return 0;
}

```
## OUTPUT:
<img width="617" height="296" alt="image" src="https://github.com/user-attachments/assets/ff7e95c9-f721-43aa-8bfa-df7fd7468e37" />

## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.
