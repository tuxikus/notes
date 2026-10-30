---
date: 2026-09-30
tags: [note, programming, rust, bevy, gamedev]
id: uvki
aliases: []
---

# Bevy Components

A component is data attached to a entity.

```rust
#[derive(Component)]
struct GridCell;

#[derive(Component)]
struct ColorOption {
    color: Color,
}
```


