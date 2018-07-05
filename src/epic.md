---
title: epic
---


```alloy
sig A{
}
sig B{
  f : set A,
  g : set A,
}
sig C{
  e : set B,
}
```

```alloy
pred epic{
  f = g <=> e.f = e.g
}
```

```alloy
pred show{
      f = g
  and epic
}

run show
```
