# EX.-NO-2-C-IMPLEMENTATION-OF-DIFFIE-HELLMAN-KEY-EXCHANGE-ALGORITHM

## AIM:
To implement the Diffie-Hellman Key Exchange algorithm using C language.

## ALGORITHM:
  
  STEP-1: Both Alice and Bob shares the same public keys g and p.
  
  STEP-2: Alice selects a random public key a.
  
  STEP-3: Alice computes his secret key A as g a mod p.
  
  STEP-4: Then Alice sends A to Bob.
  
  STEP-5: Similarly Bob also selects a public key b and computes his secret key as B and sends the same back to Alice.
  
  STEP-6: Now both of them compute their common secret key as the other one’s secret key power of a mod p.
  
## PROGRAM:
```
#include <math.h>
#include <stdio.h>

long long int power(long long int a, long long int b,
long long int P)
{
if (b == 1)
return a;
else
return (((long long int)pow(a, b)) % P);
}

int main()
{
long long int P, G, x, a, y, b, ka, kb;

printf("Enter the value of P:");
scanf("%lld",&P); 
printf("The value of P : %lld\n", P);
printf("Enter the value of G:");
scanf("%lld",&G); 
printf("The value of G : %lld\n\n", G);

a = 4; 
printf("The private key a for Alice : %lld\n", a);
x = power(G, a, P); // gets the generated key

b = 3; // b is the chosen private key
printf("The private key b for Bob : %lld\n\n", b);
y = power(G, b, P); // gets the generated key

ka = power(y, a, P); // Secret key for Alice
kb = power(x, b, P); // Secret key for Bob
printf("Secret key for the Alice is : %lld\n", ka);
printf("Secret Key for the Bob is : %lld\n", kb);
return 0;
}
```
## OUTPUT:
<img width="959" alt="Ex-9" src="https://github.com/user-attachments/assets/6fa2e108-ec53-420e-8d68-4a0e12d74214">

## RESULT:
  Thus the Diffie-Hellman key exchange algorithm had been successfully implemented using C
