---
date: 2026-09-30
tags: [note, programming, rust, bevy, gamedev]
id: j5q0
aliases: []
---

# Bevy Resources

A resource is global data.

```rust
#[derive(Resource)]
struct SelectedColor(Color);
```

## Register a Resource

```rust
fn main() {
    App::new()
        .add_plugins(DefaultPlugins)
        .insert_resource(SelectedColor(Color::srgb(0.95, 0.2, 0.2)))
        .run();
}
```
