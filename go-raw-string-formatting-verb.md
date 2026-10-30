---
date: 2026-10-01
tags: [note, programming, go]
id: dv9i
aliases: []
---

# Go raw string formatting verb

%#q is a Go fmt formatting verb:

- %q: quotes a string, e.g. "hello"
- #: uses a raw string literal when possible, e.g. `hello`

So:
```go
fmt.Sprintf("%#q", "hello")
```
produces:
```text
`hello`
```

It replaces manually adding backticks:
```go
fmt.Sprintf("`%s`", value)
```
while safely handling special characters and embedded backticks.
