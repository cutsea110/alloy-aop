---
title: Fun,Par and Rel
---


```alloy
sig A{
	f : set B,
}
sig B{
}
```

```alloy
pred function{
	~f.f in iden and A in B.~f
}
pred partial{
	~f.f in iden
}
pred relation{
}
```

```alloy
run function
run partial
run relation
```
