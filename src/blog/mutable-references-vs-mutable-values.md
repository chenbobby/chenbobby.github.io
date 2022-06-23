# Mutable References vs. Mutable Values

_2022-06-11_

What is the different between these two variables, `a1` and `a2`?

```rust
let a1: &mut i32 = ...

let mut a2: &i32 = ...
```

Did you figure it out?

The variable `a1` is a _mutable reference_.
`a1` is a reference to an `i32` value, and you can change that underlying `i32` value.

`a2` is a _mutable value_, the type of which is a reference.
`a2` is a reference to an `i32` value, and you can change `y` to be a reference to a different `i32` value.

Here are some examples of how `a1` and `a2` behave:

```rust
let a1: &mut i32 = &mut 800; // OK!
let a1: &mut i32 = &800;     // Error! You must use a mutable reference.

let mut a2: &i32 = &800;     // OK!
let mut a2: &i32 = &mut 800; // OK!

*a1 = 900; // OK!
*a2 = 900; // Error! You cannot change the underlying i32 value of `a2`.

a1 = &mut 900; // Error! You cannot change `a1` to a different reference.
a2 = &mut 900; // OK!
a2 = &900;     // OK!
```

**Extra Credit**

You can combine these two to get a _mutable mutable reference_.
You can think of this as a mutable reference, where the reference itself is also mutable.

```rust
let mut a3: &mut i32 = &mut 800; // OK!
*a3 = 900;                       // OK!
a3 = &mut 1000;                  // OK!
```
