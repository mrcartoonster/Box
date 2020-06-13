Automatically convert all incoming values of a particular key (at root
or any sub box) to a different type.

For example, if you wanted to make sure any field labeled 'id' was an
integer:

```python
my_box = Box(box_recast={'id': int})

my_box.new_key = {'id': '55', 'example': 'value'}

print(my_box.new_key.id, type(my_box.new_key.id))
# 55 <class 'int'>
```

If it cannot be converted, it will raise a `BoxValueError`(catachable with either `BoxError` or `ValueError` as well)

```python
my_box = Box(box_recast={'id': int})

my_box.id = 'Harry'

# box.exceptions.BoxValueError: Cannot convert Harry to <class 'int'>
```
