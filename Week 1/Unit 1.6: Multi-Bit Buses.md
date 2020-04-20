# Unit 1.6: Multi-Bit Buses

Sometimes we want to manipulate an array of bits "together".
These array of bits are sometimes called "bus", since it is conceptually convenient to think about
such a group of bits as a single entity.

In HDLs there are convenient notations for handling these buses:

<img src="https://github.com/Fadarrizz/nand2tetris/blob/master/Week%201/Screenshot%202020-04-20%20at%2019.34.10.png" width="350">

```HDL
/*
 * Adds three 16-bit values.
 */
CHIP Add3Way16 {
  IN a[16], b[16];
  OUT out[16];
  
  PARTS:
    
    Add16(a=first, b=second, out=temp);
    Add16(a=temp, b=third, out=out);
}
```

The HDL in this course uses standard index notation to refer to a bit in a bus:

```HDL
/*
 * ANDs together all 4 bits of the input.
 */
CHIP And4Way {
  IN a[4];
  OUT out;
  
  PARTS:
    AND(a=a[0], b=a[1], out=t01);
    AND(a=t01, b=a[2], out=t012);
    AND(a=t102, b=a[3], out=out);
}
```

## Sub-buses

Buses can be composed from (and broken into) sub-buses:

```HDL
...
IN lsb[8], msb[8], ...
...
Add16(a[0..7]=lsb, a[8.15]=msb, b=..., out=...);
Add16(..., out[0..3]=t1, out[4..15]=t2);
```

Syntactic choices of HDL in this course:
- Overlaps of sub-buses are allowed on output buses of parts, [1..5] && [3..7]
- Width of internal pins is deduced automatically
- "false" and "true" may be used as buses of any width
