Ownership is the rules for how [[Rust]] manages memory. The system of ownership has a set of rules that the compiler checks. If the rules aren't met then the program will not compile.

## The ownership rules
- Each value in Rust has an owner
- There can only be one owner at a time
- When the owner goes out of scope, the value is dropped