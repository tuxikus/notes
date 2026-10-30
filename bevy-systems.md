---
date: 2026-09-30
tags: [note, programming, rust, bevy, gamedev]
id: u6in
aliases: []
---

# Bevy Systems

A system is a rust function that bevy calls.

```rust
fn read_color(selected_color: Res<SelectedColor>) {
    let color = selected_color.0;
}
```

## Register a system

```rust
fn main() {
    App::new()
        .add_plugins(DefaultPlugins)
        .add_systems(Update, read_color)
        .run();
}
```
