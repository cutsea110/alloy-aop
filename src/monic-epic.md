---
title: monic and epic not implies iso
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
fun dom(f: univ -> univ) : univ{
	f.univ
}
fun cod(f: univ -> univ) : univ{
	univ.f
}
pred iso(f: univ -> univ){
	~f.f in iden
}

pred function{
	partial
	and
	D in dom[h] and D in dom[k] and C in dom[me] and B in dom[f] and B in dom[g]
}
pred partial{
	iso[f] and iso[g] and iso[me] and iso[h] and iso[k]
}
pred relation{
}
```

```alloy
assert function_iso{
	function and me_monic and me_epic implies me_iso
}
check function_iso for 10

assert partial_iso{
	partial and me_monic and me_epic implies me_iso
}
check partial_iso for 10

pred theorem{
	me_monic and me_epic and !me_iso
}

pred show {
	theorem
	and h.me = k.me
	and me.f = me.g
	and #A > 1
	and #D > 1
	and #B != #C
}
run show
```
