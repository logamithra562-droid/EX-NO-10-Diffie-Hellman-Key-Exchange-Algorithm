# EX-NO-10-Diffie-Hellman-Key-Exchange-Algorithm

## AIM:
To Implement Diffie Hellman Key Exchange Algorithm 

## Algorithm:

1. Diffie-Hellman Key Exchange is used for securely sharing a secret key between two parties over an insecure channel.

2. Initialization: Agree on a large prime number \( p \) and a primitive root \( g \) modulo \( p \) (both are public values).

3. Key Exchange Process: 
   - Each party selects a private key and calculates their public key using the formula \( g^{\text{private key}} \mod p \).
   - Each party then shares their public key with the other.

4. Secret Key Computation: 
   - Each party computes the shared secret key using the received public key and their own private key.

5. Security: The difficulty of computing discrete logarithms ensures that the shared key remains secure even if public values are intercepted.

## Program:
~~~
#include <stdio.h>

int main()
{
    int p = 23, g = 5;
    int a = 6, b = 15;
    int A, B, key1, key2;

    // Calculate public keys
    A = 1;
    for(int i = 0; i < a; i++)
        A = (A * g) % p;

    B = 1;
    for(int i = 0; i < b; i++)
        B = (B * g) % p;

    // Calculate shared secret keys
    key1 = 1;
    for(int i = 0; i < a; i++)
        key1 = (key1 * B) % p;

    key2 = 1;
    for(int i = 0; i < b; i++)
        key2 = (key2 * A) % p;

    printf("Public key of A: %d\n", A);
    printf("Public key of B: %d\n", B);
    printf("Shared secret key of A: %d\n", key1);
    printf("Shared secret key of B: %d\n", key2);

    if(key1 == key2)
        printf("Key Exchange Successful");
    else
        printf("Key Exchange Failed");

    return 0;
}
~~~
## Output:
<img width="1702" height="1076" alt="image" src="https://github.com/user-attachments/assets/876dc0c8-f33c-452b-ada6-a1d5042d9e67" />



## Result:
  The program is executed successfully

