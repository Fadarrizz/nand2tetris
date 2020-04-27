# Negative numbers

 ## Sign bit
 To represent negative numbers, the last bit is used as a sign. O means positive, 1 means negative.
 If we have `1001`, that means -1.
 
 *Usually, sometime that is not elegant, is going to bite you.*
 
 With this representation, `1000` would mean -0, which is the same as 0. This would give problems.
 
 ## 2's Complement
 Instead of the representation above, what is used most of the time is 2's Complement. With this a 
 negative number is represented as: 2<sup>n</sup>-X.
 
 **Positive numbers in range: 0 ... 2<sup>n-1</sup>-1**
 - 0000 0
 - 0001 1
 - 0010 2
 - 0011 3
 - 0100 4
 - 0101 5
 - 0110 6
 - 0111 7
 
 **Negative numbers in range: -1 ... -2<sup>n-1</sup>**
 - 1000 -8
 - 1001 -7
 - 1010 -6
 - 1011 -5
 - 1100 -4
 - 1101 -3
 - 1110 -2
 - 1111 -1
 
 ## Addition in 2's Complement
 Let's suggest the following:
 
 ```
  -2      14      1110
 +      +       +
  -3  =   13  =   1101
 ---    ----     -----
  -5      11     11011
 ```
 
 -2 + -3, using 2's Complement, equals to 14 + 13. In binary that equals to: `1110 + 1101 = 11011`.
 `11011` equals to 27. But in this case we only have 4 bits to our disposal, so we can discard the 
 carry. That results in `1011`, which equals to 11. The nice thing about 2's Complement is that equals
 to -5, which is the result we are expecting.
 
 So, with 2's Complement we get subtraction for free.
 
 Addition is modulo 2<sup>n</sup>.
 
 ## Computing Negation
 Input: x
 Output: -x (in 2's complement)
 
 Idea: 2<sup>n</sup> - x = 1 + (2<sup>n</sup> - 1) - x
 
 `11111111` = 2
```
  11111111
- 10101100
  --------
  01010011
```
 
 **Example**
 Input: 4
 Output: -4 (12 or 1100 in 2's complement)
 
 - We subtract the all-one (1111) by the input (by flipping the bits)
 - Then we add one
 - The result is our output
 
```
  1111
- 0100
  ----
  1011
+    1
  ----
  1100 = 12, or -4
```
 
 To add 1, we flip the bits from right to left, stopping the first time 0 is flipped to 1.
 
