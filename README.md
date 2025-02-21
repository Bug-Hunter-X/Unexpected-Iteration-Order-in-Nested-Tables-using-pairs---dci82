# Lua Nested Table Iteration Bug

This repository demonstrates a potential issue with Lua's `pairs` iterator when used on deeply nested tables.  Modifying a table while iterating over it with `pairs` can lead to unpredictable results, potentially skipping elements or entering an infinite loop.

The `bug.lua` file contains code that showcases this problem. The `bugSolution.lua` file presents a solution using a different iteration technique that avoids this pitfall.

## Problem
The `pairs` iterator doesn't guarantee any specific order, and its behavior might be undefined if the table is structurally changed during iteration.

## Solution
The solution uses a recursive function and an explicit stack to track the elements that must be processed, ensuring that no element is accidentally missed and preventing infinite loops.