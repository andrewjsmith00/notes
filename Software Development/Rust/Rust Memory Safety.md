In [[Rust]], when the following happens:
```rust
let s1 = String::from("hello")
let s2 = s1
```
the compile fails as [[Rust]] invalidates `s1`. The reason for this is that, since `s1` is a [[Pointer]] to a value in the [[Heap]], when Rust reaches the end of the [[Variable Scope]] it means a double free can occur. To prevent this, `s1` is invalidated.