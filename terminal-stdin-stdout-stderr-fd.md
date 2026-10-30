---
date: 2026-10-30
tags: [note, programming, terminal]
id: pq8d
aliases: []
---

# Terminal stdin stdout stderr fd

[[file-descriptors]] of stdin, stdout and stderr are the following:

```go
	fmt.Println(os.Stdin.Fd())  // => 0
	fmt.Println(os.Stdout.Fd()) // => 1
	fmt.Println(os.Stderr.Fd()) // => 2
```
