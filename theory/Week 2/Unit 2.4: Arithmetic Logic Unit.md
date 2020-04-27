# Arithmetic Logic Unit

Von Neumann described a diagram in which we explained how a computer system can be built. This became
known as the Von Neumann Architecture. In this diagram he described that the ALU is a important part 
of the CPU.

If all details are obstructed and we focus only on the ALU, we can think of an abstraction which 
receives two multi-bit inputs. The third input of the ALU is a function, which the ALU computes the 
two inputs on and outputs the result.

The function is one of a family of pre-defined arithmetic and logic functions.

## The Hack ALU

<img scr="#" width="500" alt="ALU truth table">

**Inputs**
- x[16], y[16]
- zx = zero the x input
- nx = negate the x input
- zy = zero the y input
- ny = negate the y input
- f  = function code: 1 for Add, 0 for And
- no = negate the out output

**Outputs**
- out[16]
- zr = true iff out=0
- ng = true iff out<0

**Function**
- if zx then x = 0      -   16-bit zero constant
- if nx then x = !x     -   bit-wise negation
- if zy then y = 0      -   16-bit zero constant
- if ny then y = !y     -   bit-wise negation
- if f then out = x + y -   integer 2's complement addition
    - else out = x & y  -   bit-wise And
- if no then out = !out -   bit-wise negation
- if out=0 then zr = 1 else zr = 0 -  16-bit eq. comparison
- if out<0 then ng = 1 else ng = 0 -  16-bit neg. comparison

*Simplicity is the ultimate sophistication.* -- Leonardo da Vinci
