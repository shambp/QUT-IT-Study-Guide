# Week 1
## Counting binary
unlike humans who count within base 10 (0-9); computers count in base 2, or binary (as discussed previously). Which brings the question of how do we count above 1?
binary is a positional numeral system, where each digit is multiplied by 2^the position in the array, for example:

| 0 | 1 | 0 | 0 | 1 | 1 | 0 | 0 |
|-----|-----|-----|-----|-----|-----|-----|-----|
| 2^7 | 2^6 | 2^5 | 2^4 | 2^3 | 2^2 | 2^1 | 2^0 |

Once we map the byte to their respective values, we can add them all together:
(0 * 2^7) + (1 * 2^6) + (0 * 2^5) + (0 * 2^4) + (1 * 2^3) + (1 * 2^2) + (0 * 2^1) + (0 * 2^0) = 76

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

## One's complement
one's complement is another way in which we can create negative numbers, we represent this through inverting all of the bits (1 to 0 and 0 to 1).

```10000000 becomes 01111111```

to express this mathematically: ```N~ = (2^n - 1) - N```

the range of values that can be represented are the same as signed magnitude. One's compliment has the same disadvantages (minus the arithmetic issues), while gaining the advantage of having addition being performed using standard binary addition with end-around carry.

## Two's complement
an evolution of One's compliemnt this form of complement we assign a negative weighting to the msb in our sequence. two's complement numbers which have their msb set to 1 will be negative. we then calculate by doing the one's compliment +1

```
Example:
10101100
the first value is 1, therefore negative
-2^7 + 2^5 + 2^3 + 2^2
-84 + 1
n = -83

01010011
first value is 0
2^6 + 2^4 + 2^1 + 2^0
n = 83
```

Two's complement is the most common way of representing signed numbers. It also covers the weaknesses found within thte other 2 optionst that we have. There is only one way to show zero, addition is the exact same and the range of the numbers we can represent is increased by 1. To express this range mathematically: ``````2^n-1 to +((2^n-1) - 1)``````

## Tutorial
week 1 was all about setting up your IDE and getting familar with the documentation, content literally done in 20 mins

# Week 2
## bitwise operations
its time to get used to logic gates, and how they can set, flip and clear bits.
[Basic guide to logic gates](https://www.tutorialspoint.com/computer_logical_organization/logic_gates.htm)

### OR
Setting bits is done with the OR operation, for example
```
first we get our number
00100110

if i wanted to change the 7th,1st and 0th position i would:
00100110
OR 01000011
will give us the result of:
01100111
```

### AND
to clear a bit, we will do the same thing using the AND operation.
```
if we take the number we just made
01100111

but I changed my mind, i want it to go back to nomrmal. I would::
01100111
AND 00100110

would then bring me back to my number of 00100110
```

### XOR
toggling a bit again is the same concept, I changed my mind again and i thinki want to put it back to how it was after the or operation.
```
00100110
xor 01000001
    01100111
```

### One's/Two's compliment
Done through the NOT and NEG command respectively
```
NOT 01000110
outputs 10111001

NEG 01000110
outputs 10111010
```

### Logical and arithmetic shifts
this action will shift all the bits one position to the left or right. 

Logical shifts are useful for efficient multiplication (left)/division (right) of integers to the power of 2

Arithmetic shifts are useful for multiplying and dividing signed integers by powers of 2 
```
Logical shifts
LSL 00100110 (38)
outputs 01001100 (76)

RSL 00100110 (38)
outputs 00010011 (19)

Arithmetic Shifts
ASR 10100110
outputs 11010011
^ everything gets shifted right, and the MSB remains in its position

LSR 10100110
outputs 01000110
```

### Rotations
rotatations is another way to shift the bits in either direction, the difference to out logical and arithmetic shifts is that the 7th or 0th bit will wrap around to the other side depending on what rotations we use. we use something called the carry bit to store and then place at the right position depending on the direction of rotation.
```
ROL 10010110
outputs 00101101

ROR 10010110
outputs 01001011
```

## Binary arithmetic
### addition
the computer does the addition for you, pretty simple, use the + operator with your 0bx and 0by to get 0bz, where x,y and z are your bytes
### overflow/the carry bit
when storing the result of addition, we require n+1 bits at most. This is due to some additions **overflowing** (going past 0b11111111 or 0xFF). This extra bit is stored in the carry bit.
#### Avoiding Overflow
we can avoid overflow in 8 bit arithmetic by using 16 bit operands and padding the values with multiple zeros (0000000010110011).
### multi-byte arithmetic
if we need to perform calculations that are wider than our hardwares architecutre, multiple operations are required. Most of these opersations the carry bit is used to facilitate this.
```
we have 2 bytes that have been padded.
0b0000001111101000 + 0000011111010000

our first step is to add the lower section
11101000 + 11010000
= 1 10111000
then we add the high bytes + the carry bit
00000011 + 00000111 + 10000000
0 00001011

totalling out to 0b00001011 10111000
```

### Subraction
binary subraction is done through Two's complement
```
0b01100100 - 0b00110010
change it to twos complemtn
0b01100100 + 0b11001110
and then you just add then together
```

### Multiplication
binary multiplication is easily understood as the sum of a set of partial products, when doing multiplication we usually do it within the nibbles 4 bits * 4 bits.
```
1101 *
1001 =
1101 is our first sum
we then do 1101 * 1000
giving us 1110101 as our result
```

### Division & other fucntions
division, square roots and other fucntions are very expensive to implemtn on hardware, and are not found on convential ALUs

some techniques that we can use to avoid division operators are as follows
- division can be implementedusing a multiplier if the divisor can be converted to its reciprocal
 - 250 / 22 = 250 * (1/22)
 - dividing by powers of 2 can be implemented using shifts

# Week 3 

## discretisation
in any real world system we always ened to translate at some point between analogue and figial signals, that being continous and bits respectively. The transfer between each state is what we call discretisation.

## logic levels
we most commanly use the voltage level applied to/by a microcontroller pin to represent a logical level