It\'s boxes all the way down. At least, when you specify
`default_box=True` it can be.

```python
empty_box = Box(default_box=True)

empty_box.a.b.c.d.e.f.g
# <Box: {}>

# BOX 4.1 change, on lookup the sub boxes are created
print(empty_box)
# <Box: {'a': {'b': {'c': {'d': {'e': {'f': {'g': {}}}}}}}}>

empty_box.a.b.c.d.e.f.g = "h"
empty_box
# <Box: {'a': {'b': {'c': {'d': {'e': {'f': {'g': 'h'}}}}}}}>
```

Unless you want it to be something else.

``` {.python}
evil_box = Box(default_box=True, default_box_attr="Something Something Something Dark Side")

evil_box.not_defined
# 'Something Something Something Dark Side'

# Keep in mind it will no longer be possible to go down multiple levels
evil_box.not_defined.something_else
# AttributeError: 'str' object has no attribute 'something_else'
```

`default_box_attr` will first check if it is callable, and
will call the object if it is, otherwise it will see if has the
[copy]{.title-ref} attribute and will call that, lastly, will just use
the provided item as is.

4.1 Update: Previous versions had an error when something that evaluated
to None would also return a box, such as an empty string or empty list.
This behavior has been fixed.
