---
date: 2026-09-30
tags: [note]
id: sjzc
aliases: []
---

# Bevy coordinates

## Window coordinates

This is what the mouse reports:

```text
window coordinates
(0,0) ───────────────► x
  │
  │
  ▼ y
```

## World coordinates

This is where the objects live:

```text
             +y
              ▲
              │
   -x ◄───────┼───────► +x
              │
              ▼
             -y
```
