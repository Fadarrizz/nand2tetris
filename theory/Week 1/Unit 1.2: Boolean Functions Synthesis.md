# Unit 1.2: Boolean Functions Synthesis

## Truth Table to Boolean Expression

We when want to design a computer, we need to extract boolean expression into a formula.

To go from a Truth Table to a Boolean Expression, we can write an expression for each row where the output of the 
function equals 1:

x | y | z | f
--- | --- | --- | ---
0 | 0 | 0 | 1
0 | 0 | 1 | 0
0 | 1 | 0 | 1
0 | 1 | 1 | 0
1 | 0 | 0 | 0
1 | 0 | 0 | 1
1 | 0 | 1 | 0
1 | 1 | 0 | 0

Row 1 = `(NOT(x) AND NOT(y) AND NOT(z))`

Row 3 = `(NOT(x) AND y AND NOT(z))`

Row 6 = `(x AND NOT(y) AND NOT(z))`

Now that we have functions to get a value of 1 for each row. How do we get to one formula, instead of 3 separate ones?
We can place an OR expression between all the functions:

`(NOT(x) AND NOT(y) AND NOT(z))` `OR`

`(NOT(x) AND y AND NOT(z))` `OR`

`(x AND NOT(y) AND NOT(z))`

By placing an OR expression, we will get 1 where we want a 1 as value, and 0 where we want a 0 as value.

## NAND

In order to reduce the amount of operations in an expression, we have to prove that some are not necessary.

When an expression contains only AND and NOT operations, OR doesn't have to be used.

**Proof:**
`(x OR y)` = `NOT(NOT(x) AND NOT(Y))`

The AND and NOT operations cannot be reduced. But there is another operation that by itself suffice to
compute any boolean function.

**NAND**

x | y | NAND
--- | --- | ---
0 | 0 | 1
0 | 1 | 1
1 | 0 | 1
1 | 1 | 0

`(x NAND y)` = `NOT(x AND y)`


With NAND operations we can represent any boolean function.

**Proof:**

1) `NOT(x)` = `(x NAND x)`

2) `AND(x)` = `NOT(x NAND y)`
