Want to show off your box without worrying about others messing it up?
Freeze it!

```python
frigid = Box(data={'Python': 'Rocks', 'inferior': ['java', 'cobol']}, frozen_box=True)

frigid.data.Python = "Stinks"
# box.BoxError: Box is frozen

frigid.data.Python
# 'Rocks'

hash(frigid)
# 4021666719083772260

frigid.data.inferior
# ('java', 'cobol')
```

It's hashing ability is the same as the humble `tuple`, it
will not be hashable if it has mutable objects. Speaking of
`tuple`, that's what all the lists becomes now.
