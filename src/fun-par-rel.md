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
	~f.f in iden
}
```

```alloy
pred show{
	function
}

run show
```
