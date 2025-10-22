---
Par: "[[index]]"
---
---

> [!example]- Inbox
> ```dataview
> LIST
> FROM [[]] and !outgoing([[]])
> ```
# Content

```base
views:
  - type: table
    name: Table
    filters:
      and:
        - MOC == "Linux MOC"

```
