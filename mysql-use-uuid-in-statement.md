---
date: 2026-10-05
tags: [note]
id: h99p
aliases: []
---

# mysql-use-uuid-in-statement

```sql
CREATE TABLE `users` (
       `id`   INT          NOT NULL AUTO_INCREMENT PRIMARY KEY,
       `uuid` binary(16)   NOT NULL,
       `name` VARCHAR(64)  NOT NULL,
);
```

```sql
SELECT COUNT(*) FROM users WHERE uuid = UUID_TO_BIN('01a10b37-6f6d-7ee9-b00c-42a3d264bbf2');
```
