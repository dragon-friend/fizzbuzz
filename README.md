# fizzbuzz
A normal fizzbuzz in normal C  
needs -Wno-conditional-type-mismatch to compile without warnings  
only works on 64bit little endian systems, I assume  
tested on x86_64 with both glibc and musl, and riscv64 with glibc

```c
#include <stdio.h>

void fizzbuzz64(n)
{
        for(unsigned long long a=1,b,c,d;
            b=!(a%3)+(!(a%5)<<1),
            c=((0x7A7A7542ULL&-((b&2)>>1))<<(32&-(b==3)))+(0x7A7A6946&-(b&1)),
            d=0xA73382E25+(0x2343E00&-!b),
            a<=(unsigned long long)n;
            a+=!!printf((const char*)&d,
            b?(char*)&c:a));
}
```
line breaks added to improve readability
