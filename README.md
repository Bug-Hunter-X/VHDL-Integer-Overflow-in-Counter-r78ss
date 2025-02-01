# VHDL Integer Overflow Bug

This repository demonstrates a common error in VHDL: integer overflow in a counter.  The `buggy_counter.vhdl` file contains a counter that uses the `integer` type. When the counter reaches its maximum value (15 in this case), the next increment results in undefined behavior depending on your simulator/synthesizer. The `fixed_counter.vhdl` file shows a corrected version using `unsigned` which wraps around gracefully.

## Bug Description

Integer types in VHDL behave differently than in many other languages; when they overflow, the result is not clearly defined by the standard, and it will vary based on the specific tool used for simulation and synthesis. This can lead to difficult-to-debug timing issues and unexpected results.

## Solution

The solution is to use the `unsigned` type instead of `integer`.  `unsigned` provides a well-defined wraparound behavior when it overflows.