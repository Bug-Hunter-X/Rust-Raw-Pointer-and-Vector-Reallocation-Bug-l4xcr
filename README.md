# Rust Raw Pointer and Vector Reallocation Bug

This repository demonstrates a common error in Rust when working with raw pointers and vectors. Modifying a vector through a raw pointer after the vector has been reallocated can lead to unexpected and undefined behavior.

## Bug Description
The `bug.rs` file contains code that attempts to modify a vector's first element using a raw pointer. The problem arises when the vector's capacity is exceeded, triggering a reallocation. The raw pointer becomes invalid, and the subsequent write operation leads to data corruption or a program crash. 

## Solution
The `bugSolution.rs` file provides a safe and correct solution that utilizes vector indexing instead of raw pointers.  Vector indexing guarantees memory safety and prevents undefined behavior.

## How to Reproduce
1. Clone this repository.
2. Navigate to the directory.
3. Compile and run `bug.rs`: `rustc bug.rs && ./bug` (Expect undefined behavior).
4. Compile and run `bugSolution.rs`: `rustc bugSolution.rs && ./bugSolution` (Expect correct output).