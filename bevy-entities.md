---
date: 2026-09-30
tags: [note, programming, rust, bevy, gamedev]
id: lv95
aliases: []
---

# Bevy Entities

An entity is just an identifier. It represents an object in a game/programm.

```rust
commands.spawn((
    Sprite::from_color(Color::srgb(1.0, 0.0, 0.0), Vec2::splat(24.0)),
    Transform::from_xyz(0.0, 0.0, 0.0),
));
```

This creates an entity and attaches the Sprite and Transform component.
