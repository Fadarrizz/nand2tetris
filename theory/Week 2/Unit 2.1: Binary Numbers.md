# Binary Numbers

## Binary -> Decimal
b<sub></sub> b<sub>n-1</sub> b<sub>n-2</sub> ... b<sub>1</sub> b<sub>0</sub>

= ∑<sub>i</sub> b<sub>i</sub> • 2<sup>i</sup>

Maximum with k bits is:
1 + 2 + 4 + ... + 2<sup>k-1</sup> = 2<sup>k</sup>-1

## Negative numbers
When we have 8 bits, we have room for 256 different numbers. Half of this capacity is reserved for negative numbers. In the end, we have 127 different positive numbers.

## Decimal -> Binary
When converting a decimal number to a binary number, we start by finding the largest power of 2 that fits in the decimal number. For the remainder of the number, we continue finding the largest power of 2 until it sums up to the decimal number.

87 = 64 + 16 + 4 + 2 + 1 = 0101 0111 
