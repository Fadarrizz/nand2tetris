# Unit 1.4: Hardware Description Language

## Design: from requirement to interface

``` HDL
/** XOR gate: out = (a AND NOT(b)) OR (NOT(a) AND b)) */

CHIP XOR {
  IN a, b;
  OUT out;
  
  PARTS:
  // Implementation goes here
}
```

When we draw a HDL-diagram, we draw a dashed box. This box represents the Gate Interface, and thus the user's view. Inside is the implementation of the interface, which the user will not see.

Then, we place our operations inside the interface and connect them. Each connection, from one operator to another, needs to be named.

Let's say the input is A. If we connect a NOT operator to A and AND operator to the NOT operator, we have to name the connection between the NOT and AND operator. We do this by provinding the output of the first operator, in this case the NOT operator. So we call the connection from NOT to AND 'not a', since this is the output of the NOT operator with A as input.
