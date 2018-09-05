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
	f.m = g.m implies f = g
--  f = g <=> f.m = g.m
}
```

```alloy
pred show{
	monic
--	!monic
--	and f = g
	and f.m = g.m
	and #A > 1
}

run show
```
