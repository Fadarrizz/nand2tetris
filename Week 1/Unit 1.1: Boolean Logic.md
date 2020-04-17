# Unit 1.1: Boolean Logic

## Boolean Operations

(x AND y)
  
 X | Y | AND
 --- | --- | ---
 0 | 0 | **0**
 0 | 1 | **0**
 1 | 0 | **0**
 1 | 1 | **1**

 
 (x OR y)
 
  X | Y | OR
 --- | --- | ---
 0 | 0 | **0**
 0 | 1 | **1**
 1 | 0 | **1**
 1 | 1 | **1**


NOT(x)

x | NOT
--- | ---
0 | **1**
1 | **0**

## Boolean Expressions

`NOT(0 OR (1 AND 1)) = NOT(0 OR 1) = NOT(1) = 0`


## Boolean Functions

One way of writing a boolean function is as a formula:

`f(x,y,z) = (x AND y) OR (NOT(X) AND z)`

Another way of writing is as a truth table:

x | y | z | f
--- | --- | --- | ---
0 | 0 | 0 | **0**
0 | 0 | 1 | **1**
0 | 1 | 0 | **0**
0 | 1 | 1 | **1**
1 | 0 | 0 | **0**
1 | 0 | 1 | **0**
1 | 1 | 0 | **1**
1 | 1 | 1 | **1**

These two ways are identical.

## Boolean Indentities

**Commutative Laws:**

`(x AND y) = (y AND x)`
`(x OR y) = (y OR x)`

**Associative Laws**

`(x AND (y AND z)) = ((x AND y) AND z)`
`(x OR (y OR z)) = ((x OR y) OR z)`

**Ditributive Laws**

`(x AND (y OR z)) = (x AND y) OR (x AND z)`
`(x OR (y AND z)) = (x OR y) AND (x OR z)`

**De Morgan Laws**

`NOT(x AND y) = NOT(x) OR NOT(y)`
`NOT(x OR y) = NOT(x) AND NOT(y)`

## Boolean Algebra

With Boolean Identities we can change the form of the formula, in order to simplify it.

```
NOT(NOT(x) AND NOT(x OR y)) =           
NOT(NOT(X) AND (NOT(X) AND NOT(y)) =      // De Morgan Law
NOT((NOT(x) AND NOT(x)) AND NOT(y)) =     // Associative Law
NOT(NOT(x) AND NOT(y)) =                  // Idempotence Law
NOT(NOT(x)) OR NOT(NOT(y)) =              // De Morgan Law
x OR y                                    // Double Negation
```

We can also use a Truth table to accomplish the same. Looking at the Truth table, we can see 
that the OR operator is at stake her

`NOT(NOT(x) AND NOT(x OR y)) =  `

  X | Y | -
 --- | --- | ---
 0 | 0 | **0**
 0 | 1 | **1**
 1 | 0 | **1**
 1 | 1 | **1**

`= x OR y`

