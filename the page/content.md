# Week 1
## Bytes, Nibbles and Bit
Computers work on 1's and 0's, we arrange them in an array of 8 bits or a Byte

```
00000000 < this is a byte
0000 < within a byte are 2 nibbles
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

this list continues up to 15 (2^4-1)

we can also do this to our 8 bit bytes
0000 0000 = 0
0000 1001 = 2^3 + 2^0 = 9 
1000 1001 = 2^7 + 2^3 + 2^0 = 137

## hexadecimal
Hexadecimal is base 16 as opposed to being base 2, therefore things are multiplied by 16^n instead of 2.

The digits used are 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F. Where A-F are just 10-15.

> little reference table 4 u

|  Hexadecimal  |  Binary   |
|-----|-----|
| 0 | 0000 |
| 1 | 0001 |
| 2 | 0010 |
| 3 | 0011 |
| 4 | 0100 |
| 5 | 0101 |
| 6 | 0110 |
| 7 | 0111 |
| 8 | 1000 |
| 9 | 1001 |
| A | 1010 |
| B | 1011 |
| C | 1100 |
| D | 1101 |
| E | 1110 |
| D | 1111 |

hexadecmial is convenient when working with digital systems since each hex digit is the size of a nibble. Example:

(the 16 just represents that this is hexadecimal btw)
- (80)16 = 1000 0000
- (B4)16 = 1911 0100

## Octal
Octal is the same has hex, but halved, using 8 instead of 16, and only going from 0-7.

## numeric literals
this refers to the way that we declare values in programming.
- no prefix is decimal notation (56)
- 0b is the prefix for binary notation (0b10101001)
- 0x is the prefix for hexadecimal (0xA6)

## Signed integers
> this is where the negative numbers come in

When doing sign magnitude representation we use the MSB to encode the sign of the integer. with 0 indicating positve and 1 being negative.
- 00000001 is 1
- 10000001 is -1

something to note is that when doing a sign bit encoded sequence, the msb is consumed. changing our little range equation thing into:

```-((2^n-1) - 1) to +((2^n-1) - 1)```

### issues with signed integers
there are a few issues with sign magnitude:
- there are two ways to represent 0 (0b00000000, 0b10000000)
- arithmetic and comparison requires inspection of the sign bit
- the range of numbers you can work with are reduced

## One's complement
one's complement is another way in which we can create negative numbers, we represent this through inverting all of the bits (1 to 0 and 0 to 1).
```
10000000 becomes 01111111
```

to express this mathematically:
```
~N~ = (2^n - 1) - N
```

## Two's complement