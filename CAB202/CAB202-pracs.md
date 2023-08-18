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

## Tutorial
# Week 3 
## Logic Levels
### discretisation
in any real world system we need to translate some kind of analogue ( continuous) into a digital signal (bits) or vice versa. When we translate this its called **discretisaion**

### Logic Levels in Inputs
in an ideal world, we would have 2 inputs, one being for a high voltage input and a low vlotage input, with a clear zone in between that does not accept inputs. We do this through the use of thresholds. a vlotage above the input high threshold is considered high or logical 1, with its low counterpart being logical 0

### Hysteresis
refers to the property of a system which has a state dependent on its history.

When an inputer is in the low state, we would not consider it to have transisiotned to the hihg state until the voltage crosses the high input voltage threshold. once it crosses our high threshold, it would cross over to high.

Essentially hysteresis is a method of discretisation that uses logical 1 and 0, with a threshold being place somehere to swap between them both. (would strongly suggest looking at the graphs in the sliedes if you have issues understanding)

## electrical quantitites
there are 3 ways that we want to measure electricity.
#### Voltage
Measures the electric potnetial difference two points in a circuit. which is measured in volts (V)
- it represents the **potential** of the electrical system to do work
- commonly measured with respect to ground (or 0V)
- by convention we use the variable _v_ to represent voltage
#### Current
current measures the rate of flow of electrical charge trhough a circuit, in Amps (A)
- by convention we use the variable _i_ to represent the current
#### Power
is the rate of energy transferral per unit time, measured in watts
- in an electrical circuit, power is given through the equation
>> P = v * i

## Ohm's Law
resistence is the property of a circuit that opposes the flow of current
- measured in ohms
- we usually assume that the wires that connect elements of our circuit are _ideal_ or have no resistance.
- ohms law describes the relationship between voltage, current and resistance, represented with the equation
>> v = i * R
>> where R is the resistance in the system

## Basic Circuit Elements
within cab202 we will be working with resistors, switches and LEDS

all other circuit elements are reated as black boxes

### switches
im not going to explain this, works the same as ur light switch

### diodes
diodes are a kind semiconductor which will only allow electricity to flow in one direction, this is done with the use of a anode and a cathode, with the flow being from anode -> cathode

### Integrated circuits
a set of electronic circuits implemented on a single piece of a semiconductor materail (usually silicon).

## Digital output interfacing
while all digital outputs are designed to bea ble to drive connected circuits to one of the two states (those being high and low, referred to at the beginning of week 3), the appropriate technique to get there is specific based on context:
- what wort of loads is this output required to drive
- could more than one device be attempting to actively drive the net to a specific logic level?

we call common points of connection for multiple components a **net**.

### Push-pull outputs
a push pull digital output is the most common form of ourput, and is commonly formed using two transistors which act like switches.
- one connected to the high
- and the other connected to the low

The output state is determined by the logic level of the input. a push pull output can both source and sink current from the connected net.

### High impedence outputs
in many scenarios it is required for a digital output to be put into a hi impedence (HiZ) state. when outputting HiZ, the rest of the circuitry will view it as an open circuit (as if the output was completely disconnected from the system).

When a figital output is in a HiZ state, the voltage on the output will be determined by whatever other circuitry is connected to that output

we would want to use HiZ inputs when multiple devices need to signal over the same wire.

### Pull-up, Pull-down resistors
in circumstances where it might be possible that there isnt a device actively driving a net high or all (for example if all of our connected outputs are currently in the HiZ state) we might like ot ensure that the state of the pin is always well-defined using a pull up or pull down resistor

these resistors tehn to have have a high value (within the range of a kilo-ohm (i think thats what their notation is saying dont quote me on that)). When there is no other circuitry driving the net, the reistor will either pull the voltage up or down.

When another device actively drives the net, the active device defines the voltage of the net. The small effect that the resistor has on the system is sourced or sunk by the active device within the net.

multiple push pull outputs should never be connected to the same net, in the event that there is one of each present, a short circuit would result and could damage one or more of the devices.

### Open Drain ouputs
a way that we can prevent and avoid a short circuit through multiple pull up/down reistors is to use open-drain output instead. Which are either in high impedance, or simply just pulls to ground. we would use a pull up resistor in conjunction with this to pull the net to the high state as well.

## Microcontroller ports
### Microcontroller Pins
the way we interface with our controllers is through their pins, its the only way to get input and output from them. However not every pin has the same purpose:
- general purpose input and output (GPIO)
- Peripheral functions
- other misc functions like power supply

are all valid uses for mcu pins, whic hwe frequentlu organise into IO banks. when programming AVR controllers we call them ports
- ports and pins have an alphanumeric designation purely as an identifier
- ports are organised into groups of 8 pins to allow a 1-1 correspondence between bytes and pins.

### the ports on the atiny1626
- dir
 - controls push pull driver output
- out
 - controls the output state (high or low)
- in
 - is used to read the state of a pin
- internal pull-up
 - which can be software enabled
- Physical voltage on pin
 - can be routed to an analogue to digital convert (ADC)

 i would suggest looking at the diagrams for this section, shows you where they arll are and what they are for.

### configuring an atiny 1626 port

