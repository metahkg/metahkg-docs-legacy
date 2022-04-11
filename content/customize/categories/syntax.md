---
title: Syntax
pcx-content-type: concept
weight: 1
layout: list
meta:
  title: Syntax
---

# Syntax

## Types

```typescript
interface Category {
    id: number, // integer
    name: string,
    hidden?: boolean
}
```

## Hidden

If `hidden` is set as true, all posts in the category are hidden to anonymous users.

## Example

```javascript
{
    id: 8, // id is 8
    name: "Adult",
    hidden: true // category is hidden
}
```
