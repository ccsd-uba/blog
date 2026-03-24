+++
title = "Understanding Ownership in Rust"
description = "A practical guide to Rust's ownership model: what it is, how it works, and why it matters for writing safe and efficient code."
date = 2026-03-10

[taxonomies]
tags = ["rust", "programming", "systems"]

[extra]
+++

The **ownership** system is perhaps Rust's most distinctive feature. It's what allows it to guarantee memory safety *without* a garbage collector.

<!-- more -->

## What is ownership?

In Rust, every value has a single **owner**. When the owner goes out of scope, the value is automatically freed. No GC, no manual `free()`.

There are three fundamental rules:

1. Each value has exactly one owner.
2. There can only be one owner at a time.
3. When the owner goes out of scope, the value is dropped.

## A simple example

```rust
fn main() {
    let s1 = String::from("hello");
    let s2 = s1; // s1 is moved to s2

    // This would cause a compile error:
    // println!("{}", s1); // error: value moved

    println!("{}", s2); // OK
}
```

Unlike languages like Python or Java, here there aren't two references to the same string. The value was **moved** from `s1` to `s2`.

## Borrowing: using without giving up ownership

If you want to use a value without transferring ownership, you use references:

```rust
fn main() {
    let s1 = String::from("world");
    let len = calculate_length(&s1); // we borrow s1
    println!("Length of '{}': {}", s1, len); // s1 is still valid
}

fn calculate_length(s: &String) -> usize {
    s.len()
}
```

The `&` indicates it's a **reference** (borrow). The `calculate_length` function can use `s` but doesn't have ownership of it.

## Mutable references

```rust
fn main() {
    let mut s = String::from("hello");
    add_world(&mut s);
    println!("{}", s); // "hello, world"
}

fn add_world(s: &mut String) {
    s.push_str(", world");
}
```

Important rule: **only one mutable reference can exist at a time** in the same scope. This prevents data races at compile time.

## Why does this matter?

This system makes Rust incredibly safe: it's impossible to have dangling pointers, use-after-free, or data races — and everything is detected at compile-time, with zero runtime cost.

In the next post, we'll talk about **lifetimes**, which are the natural extension of this system for handling references with different lifespans.
