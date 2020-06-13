`Box` can be instantiated the same ways as
`dict`.

```python
Box({'data': 2, 'count': 5})
Box(data=2, count=5)
Box({'data': 2, 'count': 1}, count=5)
Box([('data', 2), ('count', 5)])

# All will create
# <Box: {'data': 2, 'count': 5}>
```

`Box` is a subclass of `dict` which overrides
some base functionality to make sure everything stored in the dict can
be accessed as an attribute or key value.

```python
small_box = Box({'data': 2, 'count': 5})
small_box.data == small_box['data'] == getattr(small_box, 'data')
```

All dicts (and lists) added to a `Box` will be converted on
lookup to a `Box` (or `BoxList`), allowing for
recursive dot notation access.

`Box` also includes helper functions to transform it back
into a `dict`, as well as into `JSON` or
`YAML` strings or files.
