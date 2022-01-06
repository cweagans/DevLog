---
id: vcabTyefwVrYXz8JhnrKm
title: Custom
desc: ''
updated: 1641427034911
created: 1641427034911
---

### Custom Typing:

```python
from typing import List

Vector = List[float]	

def foo(v: Vector) -> Vector:
	print(v)
```

![alt](assets/images/Pasted image 20211215085306.png)

Can also use our own custom types like this: 

```python
from typing import List

Vector = List[float]
Vectors = List[Vector]

def foo(v: Vectors) -> Vectors:
	print(v)
```