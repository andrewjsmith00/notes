[[Rust]] variables are immutable. This means that once set, they cannot be changed. Writing code this way means that safety and concurrency is a lot easier to work with.

You can make variables mutable but it is not favoured.

To make a variable mutable, you can use the `mut` keyword on definition. This also means future code readers will know the variable is mutable.

For example
```rust
fn main() {
	let mut x = 5;
	println!("The value of x is {x}");
	let x = 6;
	println!("The value of x is {x}");
}
```

will compile, whereas without `mut` it fails.


## Constants
Similar to immutable variables, constants are not able to change their values. Unlike normal variables, the `mut` keyword cannot be used and the type must be annotated. The value has to be a constant as well. This allows for a method of hardcoding values and is useful for values such as max score or speed of light.

## Shadowing
Shadowing is where you re-use a variables name in scope but re-declare the variable. The compiler will pay attention to the second variable's use instead of the first and changes are only within the scope of the shadowed variables use.

To do this, the variable is simply declared again with the `let` keyword, however the original value can be used.