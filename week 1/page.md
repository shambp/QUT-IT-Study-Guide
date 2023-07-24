# Bytes, Nibbles and Bits
Computers work on 1's and 0's, we arrange them in an array of 8 bits or a Byte

```
00000000 < this is a byte
0000 < within a bit are 2 nibbles
0 < and within the nibble are 4 bits
*fyi the terminology still applies if its a 1, using all zeros is just easier
```
a single bit can only be in 2 states; 0 or 1, whereas a sequence of bits (n) can be represent up to 2^n states.
for example a byte can up to 2^8 different permutations.

unlike people who count within base 10 (0-9); computers count in base 2, or binary (as discussed previously). Which brings the question of how do we count above 1?
binary is a positional numeral system, where each digit is multiplied by 2^the position in the array
Example
```
| 0 | 1 | 0 | 0 | 1 | 1 | 0 | 0 |
| 2^7 | 2^6 | 2^5 | 2^4 | 2^3 | 2^2 | 2^1 | 2^0 |
(0 * 2^7) + (1 * 2^6) + (0 * 2^5) + (0 * 2^4) + (1 * 2^3) + (1 * 2^2) + (0 * 2^1) + (0 * 2^0) = 76
```
> Something to note is that this can also be done with negative numbers using something called Two's constant, which will be covered a tiny bit later


