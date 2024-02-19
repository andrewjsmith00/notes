A reference in [[Rust]] is guaranteed to point to a valid value of a type unlike a pointer. When you use an `&`, it represents a reference.

For example, in code like:
```rust
fn main() {
	let s1 = String::from("hello");

	let len = calculate_length(&s1);

	println!("The length of '{}' is {}.", s1, len);
}

fn calculate_length(s: &String) -> usize {
	s.len()
}
```

The function `calculate_length` takes `&String` as a parameter. This turns `s` into a pointer to `s1` which then points to the values.

When `s` drops, the values it is pointing to are not as it does not own the values. When the function returns, we don't return [[Ownership]] as we never had it in the first place.

This action of creating a reference is called **Borrowing**. We can't modify whatever is in our reference by default without creating a mutable reference, however we can only have one mutable reference at a time.