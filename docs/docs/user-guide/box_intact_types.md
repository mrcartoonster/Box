Do you not want box to convert lists or tuples or incoming dictionaries
for some reasonn? That's totally fine, we got you covered!

``` {.python}
my_box = Box(box_intact_types=[list, tuple])

# Don't automatically convert lists into #BoxList
my_box.new_data = [{'test': 'data'}]

print(type(my_box.new_data))
# <class 'list'>
```
