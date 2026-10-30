---
date: 2026-09-29
tags: [note, programming, rust]
id: ee7d
aliases: []
---

# Rust Variables

Rust variables are **immutable by default**, which helps make programs safer and easier to reason about.

## 1. Declaring Variables

Use `let` to declare a variable:

```rust
fn main() {
    let x = 10;
    println!("x = {x}");
}
```

Rust usually infers the variable's type automatically. You can also specify it explicitly:

```rust
let age: u32 = 25;
let temperature: f64 = 21.5;
let active: bool = true;
```

## 2. Variables Are Immutable by Default

This does **not** compile:

```rust
fn main() {
    let x = 5;
    x = 10; // Error
}
```

To allow a variable's value to change, use `mut`:

```rust
fn main() {
    let mut x = 5;

    println!("Before: {x}");

    x = 10;

    println!("After: {x}");
}
```

## 3. Shadowing

Rust allows you to declare a new variable with the same name:

```rust
fn main() {
    let x = 5;
    let x = x + 1;
    let x = x * 2;

    println!("{x}"); // 12
}
```

This is called **shadowing**.

Unlike `mut`, shadowing can also change the variable's type:

```rust
fn main() {
    let spaces = "   ";
    let spaces = spaces.len();

    println!("{spaces}"); // 3
}
```

With `mut`, changing the type is not allowed:

```rust
let mut spaces = "   ";
spaces = spaces.len(); // Error: expected &str, found usize
```

## 4. Constants

Constants are declared using `const`:

```rust
const MAX_USERS: u32 = 1000;

fn main() {
    println!("Maximum users: {MAX_USERS}");
}
```

Constants differ from normal variables:

* Use `const` instead of `let`.
* A type annotation is required.
* They cannot be made mutable.
* By convention, their names use [[screaming-snake-case]].

Example:

```rust
const SECONDS_PER_MINUTE: u32 = 60;
const MINUTES_PER_HOUR: u32 = 60;
const SECONDS_PER_HOUR: u32 =
    SECONDS_PER_MINUTE * MINUTES_PER_HOUR;
```

## 5. Variable Scope

A variable is valid only within its scope:

```rust
fn main() {
    let outer = 10;

    {
        let inner = 20;

        println!("{outer}");
        println!("{inner}");
    }

    println!("{outer}");

    // println!("{inner}"); // Error: inner is out of scope
}
```

## 6. Destructuring Variables

Rust can extract values from structures such as tuples:

```rust
fn main() {
    let point = (10, 20);

    let (x, y) = point;

    println!("x = {x}");
    println!("y = {y}");
}
```

You can ignore values using `_`:

```rust
let (x, _) = (10, 20);

println!("{x}");
```

## Quick Reference

| Syntax                  | Meaning                     |
| ----------------------- | --------------------------- |
| `let x = 5;`            | Immutable variable          |
| `let mut x = 5;`        | Mutable variable            |
| `let x: i32 = 5;`       | Variable with explicit type |
| `let x = x + 1;`        | Shadow an existing variable |
| `const MAX: u32 = 100;` | Constant                    |
| `let (x, y) = point;`   | Destructuring               |

### Key Idea

Rust encourages **immutability by default**:

```rust
let x = 5;      // Prefer this
let mut y = 5;  // Use when mutation is actually needed
```

This makes it clearer which values can change while a program is running.
