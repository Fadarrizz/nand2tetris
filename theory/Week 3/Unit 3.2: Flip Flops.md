# Flip Flops

## Remebering State
Missing ingredient: remember one bit of information from *t-1*, so it can used at time *t*.
At the 'end of time' t-1, such an ingredient can be at either of two states: 'rememebering 0' or 'remembering 1'.
This ingredient remembers by 'flipping' between these possible states.
Gates that can flip between two states are called Flip-Flops.

## Implemenetation of the Data Flip-Flop
In this course: it is a primitive

In many physical implementations, it may be built from actual Nand gates:
- Step 1: create a loop, achieiving an 'un-clocked' flip-flop
- Step 2: isolation across time steps using a 'master-slave' setup

## Sequential Logic Implementation
We are remembering bits in an array of flip-flops, which basically makes up all our data. We then feed this data to some combinatorial logic, which adds 1 to create a counter for example.

## Remembering For Ever: 1-bit Register
Goal: remember an input bit 'forever': until requested to load a new value.

<img src="https://github.com/Fadarrizz/nand2tetris/blob/master/theory/screenshots/Bit%20chip.png" width="300" alt="Bit chip">

If a value is feeded to a Bit chip, it has to remember it until a new value is loaded. The triangle in the image above means that it is time sensitive, meaning it is connected to a clock.

When a new value is feeded into the bit, it will be available until the next tick.

