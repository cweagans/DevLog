---
id: GQE1AXAmZDRjiOUmbppxd
title: Default Parameters
desc: ''
updated: 1641423050502
created: 1641423050502
---

## Default Parameters

```python
# In Python 3 you can use a bare "*" asterisk
# in function parameter lists to force the
# caller to use keyword arguments for certain
# parameters:

def f(a, b, *, c='x', d='y', e='z'):
return 'Hello'

# To pass the value for c, d, and e you
# will need to explicitly pass it as
# "key=value" named arguments:
f(1, 2, 'p', 'q', 'v')
# TypeError: "f() takes 2 positional arguments but 5 were given"

f(1, 2, c='p', d='q',e='v')
'Hello'
```