# Binary Addition

The only mathmatical operation we are going to implement is addition.
Once we know how to work with negative numbers, we can subtract numbers as well.

Multiplication and division are complex operations. Luckily, they are not needed in hardware,
so we can postpone it to software.

## Adition
In order to add binary numbers, we need to start at the most right numbers. We count them up and carry
over a number when it's to big for the spot we are in, just as with decimal numbers.

When we count up large decimal numbers, we also have to carry over any sum that is larger than 9.

```
+1 +1
 5 7 8 3
 2 4 5 6
         +
 -------
 8 2 3 9
```
The way we count up these numbers can also be used for counting up binary numbers.
 
```
     +1
 1 0 0 1
 0 1 0 1
         +
--------
 1 1 1 0
```

## Overflow
It can occur that the last addition causes an overflow outside the boundaries of the range of bits.

```
+1    +1+1+1
  1 0 0 1 0 1 0 1
  1 1 0 1 1 1 0 0
 ---------------- +
1 0 1 1 1 0 0 0 1
```

In computer science, this addition will not be accounted for, since we cannot exceed the limit. 
Instead, the result will be truncated in order to still fit the limit. In other words, the last will
become a zero, but the carry will be discarded.

## Building an Adder
- Half Adder - adds two bits
- Full Adder - adds three bits
- Adder - adds two numbers

### Half Adder
A half Adder outputs a sum and a carry. The sum is the binary sum of two bits. 
The carry is the binary value we want to carry over.

a | b | sum | carry
:---: | :---: | :---: | :---:
0 | 0 | 0 | 0
0 | 1 | 1 | 0
1 | 0 | 1 | 0
1 | 1 | 0 | 1

### Full Adder

a | b | c | sum | carry
:---: | :---: | :---: | :---:
0 | 0 | 0 | 0 | 0
0 | 0 | 1 | 1 | 0
0 | 1 | 0 | 1 | 0
0 | 1 | 1 | 0 | 1
1 | 0 | 0 | 1 | 0
1 | 0 | 1 | 0 | 1
1 | 1 | 0 | 0 | 1
1 | 1 | 1 | 1 | 1

### Multi-bit Adder (16-bit)
Connect 15 Full-Adders and 1 Half-Adder.

out = a + b, as 16-bit integers
(overflow ignored)
