# Week 3

In order to build chips that 'remember' information, we must first develop some standard means for representating the progression of time.

## The Clock
Most computers have a master clock dat delivers a continuous train of alternating signals. The hardware implementation is usually based on an oscillator that continuously switches between two phases, 0-1. The time between each switch is called a cycle. The current phase (tick or tock) is represented by a binary signal. This is broadcasted to every chip.

## Flip-Flops
Most elementary sequential element is a flip-flop. We are going to use a data flip-flop (DFF), whose interface consists of a single-bit data input and a single-bit data output. A DFF has a clock input that is continuously updated according to the master's clock signal. Toghether, the data and the clock input enables the DFF to implement the time-based behaviour `out(t) = in(t - 1)`, where *in* and *out* are the gate's input and output values and *t* is the current clock cycle. Simply said, the DFF outputs the input value from the previous time unit.

This behavior forms the basis of all the hardware devices that computers use to maintain state.

## Registers
A Register is a storage device that can store or remember a value over time, implementing storage behaviour `out(t) = out(t - 1)`. A DFF can only output its previous input. This suggests that a register can be implemented from a DFF by simply feeding the output of the latter back into its input.

<img src="https://github.com/Fadarrizz/nand2tetris/blob/master/theory/screenshots/DFF%20to%20register.png" width="750" alt="From a DFF to a single-bit register">

The above image shows an invalid design of a register. It is not clear how new data is loaded into the device, since there is no way to tell when the input is drawn from the in-wire and when from the out-wire. The rules of chip design dictate that internal pins must have a fan-in of 1, meaning from a single source only.

Therefore, we need to put a multiplexor into the design. With this, we can give a load bit as the select bit, telling that we want to store some new value. Thus, we input will come from the in-wire. If not, it comes from the out-wire.

This mechanism for remembering a single bit can be easily scaled to construct wide registers. This can be achieved by forming an array of single-bit registers. The multi-bit contents of such registers are typically referred to as *words*.

## Memories
Once we have the ability to represent words, we can build memory banks of all sizes. 

<img src="https://github.com/Fadarrizz/nand2tetris/blob/master/theory/screenshots/Single-bit%20to%20multi-bit%20registers.png" width="600" alt="From single-bit to multi-bit registers">

<img src="https://github.com/Fadarrizz/nand2tetris/blob/master/theory/screenshots/RAM%20chip.png" width="550" alt="RAM chip">

## Counters

## Time Matters

