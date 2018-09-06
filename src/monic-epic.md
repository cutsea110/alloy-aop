---
title: epic
---

```alloy
sig A{
}
sig B{
	f : set A,
	g : set A
}
sig C{
	me : set B
}
sig D{
	h : set C,
	k : set C
}
```

```alloy
pred monic{
	h.me = k.me implies h = k
}
pred epic{
	me.f = me.g implies f = g
}
```

```alloy
pred show {
	monic	and epic
	and h.me = k.me
	and me.f = me.g
	and #A > 1
	and #D > 1
	and #B != #C
	and me.~me not in iden
}
run show
```
