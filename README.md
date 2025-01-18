# JavaScript Closure Problem with setTimeout and Loop Variable

This repository demonstrates a common error in JavaScript related to closures and the `setTimeout` function within a loop.  The problem arises because the `setTimeout` callback function doesn't capture the value of `i` at the time it's created; instead, it captures a reference to the variable `i`. By the time the `setTimeout` callbacks finally execute, the loop has already completed, and `i` is its final value (10).

## Bug Description
The code intends to log the numbers 0 through 9 to the console with a one-second delay between each number. However, due to the closure issue, it instead logs the number 10 ten times.

## Solution
The solution uses an immediately invoked function expression (IIFE) to create a new scope for the loop variable `i` within each iteration. This ensures that each `setTimeout` callback captures its own unique copy of the variable's value at the time of its creation.