Box 4 is out, check out the [changes and
updates](https://github.com/cdgriffith/Box/blob/master/docs/4.x_changes.rst)!

`Box` is designed to be an easy drop in transparently
replacements for dictionaries, thanks to Python\'s duck typing
capabilities, which adds dot notation access. Any sub dictionaries or
ones set after initiation will be automatically converted to a
`Box` object. You can always run `.to_dict()`
on it to return the object and all sub objects back into a regular
dictionary.

```python
movie_box.movies.Spaceballs.to_dict()
{'director': 'Mel Brooks',
 'imdb stars': 7.1,
 'length': 96,
 'personal thoughts': 'On second thought, it was hilarious!',
 'rating': 'PG',
 'stars': [{'imdb': 'nm0000316', 'name': 'Mel Brooks', 'role': 'President Skroob'},
           {'imdb': 'nm0001006', 'name': 'John Candy', 'role': 'Barf'},
           {'imdb': 'nm0001548', 'name': 'Rick Moranis', 'role': 'Dark Helmet'},
           {'imdb': 'nm0000597', 'name': 'Bill Pullman', 'role': 'Lone Starr'}]}
```
