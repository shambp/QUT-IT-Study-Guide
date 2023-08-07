# Week 1
## Counting binary
unlike humans who count within base 10 (0-9); computers count in base 2, or binary (as discussed previously). Which brings the question of how do we count above 1?
binary is a positional numeral system, where each digit is multiplied by 2^the position in the array, for example:

| 0 | 1 | 0 | 0 | 1 | 1 | 0 | 0 |
|-----|-----|-----|-----|-----|-----|-----|-----|
| 2^7 | 2^6 | 2^5 | 2^4 | 2^3 | 2^2 | 2^1 | 2^0 |

Once we map the byte to their respective values, we can add them all together:
(0 * 2^7) + (1 * 2^6) + (0 * 2^5) + (0 * 2^4) + (1 * 2^3) + (1 * 2^2) + (0 * 2^1) + (0 * 2^0) = 76
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
### Subraction
### Multiplication
### Division