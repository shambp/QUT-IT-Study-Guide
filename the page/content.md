# Week 1
## Bytes, Nibbles and Bits
Computers work on 1's and 0's, we arrange them in an array of 8 bits or a Byte

```
00000000 < this is a byte
0000 < within a bit are 2 nibbles
0 < and within the nibble are 4 bits
*fyi the terminology still applies if its a 1, using all zeros is just easier
```
a single bit can only be in 2 states; 0 or 1, whereas a sequence of bits (n) can be represent up to 2^n states.
for example a byte can up to 2^8 different permutations.
### Bit ordering
We write bits left to right from the most significant bit (MSB) to the least significant (LSB). This is due to how we count binary, the LSB will be counted as the bit * 2^0, whereas the MSB will be counted as the bit * 2^L where L is the largest index in the bit (for example in a byte the msb would be bit * 2^7)
### Number representation
#### Counting binary
unlike humans who count within base 10 (0-9); computers count in base 2, or binary (as discussed previously). Which brings the question of how do we count above 1?
binary is a positional numeral system, where each digit is multiplied by 2^the position in the array, for example:
|  0  |  1  |  0  |  0  |  1  |  1  |  0  |  0  |
|-----|-----|-----|-----|-----|-----|-----|-----|
| 2^7 | 2^6 | 2^5 | 2^4 | 2^3 | 2^2 | 2^1 | 2^0 |

Once we map the byte to their respective values, we can add them all together:
(0 * 2^7) + (1 * 2^6) + (0 * 2^5) + (0 * 2^4) + (1 * 2^3) + (1 * 2^2) + (0 * 2^1) + (0 * 2^0) = 76
> the more bits that we use the higher number that we can achieve,
>
> Something to note is that this can also be done with negative numbers using something called Two's constant, which will be covered a tiny bit later
#### representation
- Any positive integer (in this case referred to as R), where R > 1 can be used as the radix or the base of a number system
- if the base is R, then we require R digits as well to represent all of the possible number
- for example
  - if r = 5
  - the required digits are 0,1,2,3,4
#### Unsigned integers
Unsigned integers represent counting numbers that are >= 0
for an n bit sized number we can represent 0 to 2^n-1.
essentially this is displaying every single counting number (0,1,2 and so on) using the array that we have
if n = 4
we can count up to 15
|  N  |  Binary representiation  |
|-----|-----|
| 0 | 0000 |
| 1 | 0001 |
| 2 | 0010 |
| 3 | 0011 |
| 4 | 0100 |
| 5 | 0101 |
| 6 | 0110 |
| 7 | 0111 |
you get the point.



