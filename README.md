# fizzbuzz
A normal fizzbuzz in normal C
needs -Wno-conditional-type-mismatch to compile without warnings
only works on 64bit little endian systems, I assume, I've only tested it on x86


```c
void fizzbuzz(n)
{
	for(int i=1;i<n;i++){
		int b=!(i%3&&i%5);
		unsigned long s=0xA6925+0xa732dc500*b;
		unsigned long z=((0x7A7A7542UL*!(i%5))<<32*!(i%3))+0x7A7A6946*!(i%3);
		printf((const char*)&s,b?(char*)&z:i);
	}
}
```
