# fizzbuzz
A normal fizzbuzz in normal C
needs -Wno-conditional-type-mismatch to compile without warnings
only works on 64bit little endian systems, I assume
tested on x86_64 with both glibc and musl, and riscv64 with glibc


```c
#include <stdio.h>

void fizzbuzz(n)
{
        for(int i=1;i<=n;i++){
                int b=!(i%3&&i%5);
                __uint128_t z=((0x7A7A7542UL*!(i%5))<<32*!(i%3))+0x7A7A6946*!(i%3);
                            z=(z<<64)+0xA6925+0xa732dc500*b;
                printf((const char*)&z,b?(char*)&z+8:i);
        }
}
```
