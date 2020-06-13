By default, Box is now a `conversion_box` that adds
automagic attribute access for keys that could not normally be
attributes. It can of course be disabled with the keyword argument
`conversion_box=False`.

```python
movie_box.movies.Spaceballs["personal thoughts"] = "It was a good laugh"
movie_box.movies.Spaceballs.personal_thoughts
# 'It was a good laugh'

movie_box.movies.Spaceballs.personal_thoughts = "On second thought, it was hilarious!"
movie_box.movies.Spaceballs["personal thoughts"]
# 'On second thought, it was hilarious!'

# If a safe attribute matches a key exists, it will not create a new key
movie_box.movies.Spaceballs["personal_thoughts"]
# KeyError: 'personal_thoughts'
```

Keys are modified in the following steps to make sure they are attribute
safe:

1.  Convert to string (Will encode as UTF-8 with errors ignored)
2.  Replaces any spaces with underscores
3.  Remove anything other than ascii letters, numbers or underscores
4.  If the first character is an integer, it will prepend a lowercase
    'x' to it
5.  If the string is a built-in that cannot be used, it will prepend a
    lowercase 'x'
6.  Removes any duplicate underscores

This does not change the case of any of the keys.

```python
bx = Box({"321 Is a terrible Key!": "yes, really"})
bx.x321_Is_a_terrible_Key
# 'yes, really'
```

These keys are not stored anywhere, and trying to modify them as an
attribute will actually modify the underlying regular key\'s value.

!!! warning 
    Duplicate attributes possible.
    If you have two keys that evaluate to the same attribute, such as
    "a!b" and "a?b" would become ab, there is no way to
    discern between them, only reference or update them via standard dictionary modification.
