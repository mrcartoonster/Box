To make sure all items added to lists in the box are also converted, all
lists are covered into `BoxList`.title-ref}. It's possible to initiate
these directly and use them just like a `Box`.

``` {.python}
from box import BoxList

my_boxlist = BoxList({'item': x} for x in range(10))
#  <BoxList: [<Box: {'item': 0}>, <Box: {'item': 1}>, ...

my_boxlist[5].item
# 5
```

**to_list**

Transform a `BoxList` and all components back into regular
`list` and `dict` items.

```python
my_boxlist.to_list()
# [{'item': 0},
#  {'item': 1},
#  ...
```
