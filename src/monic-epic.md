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
pred me_monic{
	h.me = k.me implies h = k
}
pred me_epic{
	me.f = me.g implies f = g
}
pred me_iso{
	~me.me in iden
}
```

```alloy
pred function{
	partial
	and
	D in h.C
	and
	D in k.C
	and
	C in me.B
	and
	B in f.A
	and
	B in g.A
}
pred partial{
	~f.f in iden
	and
	~g.g in iden
	and
	~me.me in iden
	and
	~h.h in iden
	and
	~k.k in iden
}
pred relation{
}
```

```alloy
pred show {
	me_monic and me_epic and !me_iso
	and relation
	and h.me = k.me
	and me.f = me.g
	and #A > 1
	and #D > 1
	and #B != #C
}
run show
```
