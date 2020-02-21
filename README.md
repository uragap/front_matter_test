### Interior Mutability: A Mutable Borrow to an Immutable Value

A consequence of the borrowing rules is that when you have an immutable value,
you can’t borrow it mutably. For example, this code won’t compile:

```rust,ignore,does_not_compile
fn main() {
    let x = 5;
    let y = &mut x;
}
```

If you tried to compile this code, you’d get the following error:

```text
error[E0596]: cannot borrow immutable local variable `x` as mutable
 --> src/main.rs:3:18
  |
2 |     let x = 5;
  |         - consider changing this to `mut x`
3 |     let y = &mut x;
  |                  ^ cannot borrow mutably
```

However, there are situations in which it would be useful for a value to mutate
itself in its methods but appear immutable to other code. Code outside the
value’s methods would not be able to mutate the value. Using `RefCell<T>` is
one way to get the ability to have interior mutability. But `RefCell<T>`
doesn’t get around the borrowing rules completely: the borrow checker in the
compiler allows this interior mutability, and the borrowing rules are checked
at runtime instead. If you violate the rules, you’ll get a `panic!` instead of
a compiler error.

Let’s work through a practical example where we can use `RefCell<T>` to mutate
an immutable value and see why that is useful.
