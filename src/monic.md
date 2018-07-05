---
title: monic
---


```alloy
sig A{
}
sig B{
  m : set A,
}
sig C{
  f : set B,
  g : set B,
}
```

```alloy
pred monic{
  f = g <=> f.m = g.m
}
```

```alloy
pred show{
      f = g
  and #A > 1
  and monic
}

run show
```
