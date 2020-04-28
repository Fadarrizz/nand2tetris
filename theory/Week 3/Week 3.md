# Week 3

In order to build chips that 'remember' information, we must first develop some standard means for representating the progression of time.

## The Clock
Most computers have a master clock dat delivers a continuous train of alternating signals. The hardware implementation is usually based on an oscillator that continuously switches between two phases, 0-1. The time between each switch is called a cycle. The current phase (tick or tock) is represented by a binary signal. This is broadcasted to every chip.

## Flip-Flops
Most elementary sequential element is a flip-flop. 
