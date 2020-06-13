A new way to traverse the Box!

```python
my_box = Box(box_dots=True)

my_box.incoming = {'new': {'source 1': {'$$$': 'money'}}}

print(my_box['incoming.new.source 1.$$$'])
# money

my_box['incoming.new.source 1.$$$'] = 'spent'
print(my_box)
# {'incoming': {'new': {'source 1': {'$$$': 'spent'}}}}
```

Be aware, if those sub boxes didn\'t exist as planned, a new key with
that value would be created instead

```.python
del my_box['incoming']
my_box['incoming.new.source 1.$$$'] = 'test'
print(my_box)

# {'incoming.new.source 1.$$$': 'test'}
```

4.1 Update: Support for traversing box lists as well!

```.python
my_box = Box({'data': [ {'rabbit': 'hole'} ] }, box_dots=True)
print(data.data[0].rabbit)
# hole
```

This does only work for keys that are already strings as of version 4.1.
