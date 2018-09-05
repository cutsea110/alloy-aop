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
	e.f = e.g implies f = g
}
```

```alloy
pred show{
	epic
--	!epic
--	and f = g
	and e.f = e.g
	and #C > 1
}

run show
```
