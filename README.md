# JavaScript Conditional Statement Bug with Null and Zero

This repository demonstrates a subtle bug in a JavaScript conditional statement that involves comparing with `null` and zero.  The function `foo` is designed to handle different cases based on the input value, but exhibits unexpected behavior with the value 0.

## Bug Description

The bug stems from the order of conditions in the `if-else if-else` chain.  The condition `x === null` correctly handles null values; however, the subsequent condition `x < 0` does not correctly handle the case when `x` is 0, resulting in 0 being treated as a positive number and returning 1.

## Bug Reproduction

1. Clone this repository.
2. Run `bug.js` using a JavaScript runtime (e.g., Node.js).
3. Observe the unexpected output for `foo(0)`.

## Solution

The solution involves restructuring the conditional statements to handle 0 appropriately, ensuring it is not incorrectly categorized as a positive value.  The solution file `bugSolution.js` demonstrates this fix.  The order of conditional statements is changed to first check if x is strictly equal to 0 and then whether it is less than 0.

## How to fix this issue

This issue can be resolved by checking for a value of 0 explicitly before checking for negative values.  This ensures that 0 is handled correctly without being incorrectly evaluated as a positive number. The updated logic correctly categorizes all three scenarios (null, negative, and non-negative).
