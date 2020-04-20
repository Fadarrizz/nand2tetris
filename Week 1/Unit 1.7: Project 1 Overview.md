# Unit 1.7: Project 1 Overview

## Multiplexor

<img src="https://github.com/Fadarrizz/nand2tetris/blob/master/screenshots/Multiplexor.png" width="250" alt="Multiplexor">

```
if (sel==o)
  out=a
 else
  out=b
```

**Truth Table**
a | b | sel | out
--- | --- | --- | ---
0 | 0 | 0 | **0**
0 | 1 | 0 | **0**
1 | 0 | 0 | **1**
1 | 1 | 0 | **1**
0 | 0 | 1 | **0**
0 | 1 | 1 | **1**
1 | 0 | 1 | **0**
1 | 1 | 1 | **1**

**Abbreviated truth table**
sel | out
--- | ---
0 | a
1 | b


### Example: using mux logic to build a programmable gate**
```
if (sel==0)
  out = (a AND b)
 else
  out = (a OR b)
```

**Mux.hdl**
```HDL
CHIP AndMuxOr {
  IN a, b, sel;
  OUT out;
  
  PARTS:
  And (a=a, b=b, out=andOut);
  Or  (a=a, b=b, out=orOut);
  Mux (a=andOut, b=orOut, sel=sel, out=out);
}
```
## Demultiplexor

- Acts like the inverse of a multiplexor
- Distributes the single input value into one of two possible destinations

## Example: Multiplexing / demultiplexing in communications networks

<img src="https://github.com/Fadarrizz/nand2tetris/blob/master/screenshots/Mux:DMux%20for%20communications%20network.png" width="800" alt="mux/dmux in communications network">

- Each `sel` bit is connected to an oscillator that produces a repetitive train of alternating 0 and 1 signals
- Enables transmitting multiple messages on a single, shared communications line
- A common use of multiplexing/demultiplexing logic

