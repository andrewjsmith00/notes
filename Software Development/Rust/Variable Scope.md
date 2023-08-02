The scope is the range for where an item is valid.

For example with the variable s:
```rust
let s = "hello"
```

`s` is valid from when it is declared until the end of the current scope. For example:

```rust
{    // s is not valid here
	let s = "hello"; //s is valid from here
}    // s is no longer valid
```

