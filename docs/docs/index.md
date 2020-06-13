# Welcome to Box
[![BuildStatus](https://travis-ci.org/cdgriffith/Box.png?branch=master)](https://travis-ci.org/cdgriffith/Box)
[![CoverageStatus](https://img.shields.io/coveralls/cdgriffith/Box/master.svg?maxAge=2592000)](https://coveralls.io/r/cdgriffith/Box?branch=master)
[![License](https://img.shields.io/pypi/l/python-box.svg)](https://pypi.python.org/pypi/python-box/)
[![PyPi](https://img.shields.io/pypi/v/python-box.svg?maxAge=2592000)](https://pypi.python.org/pypi/python-box/)
[![DocStatus](https://readthedocs.org/projects/box/badge/?version=latest)](http://box.readthedocs.org/en/latest/index.html)

[![BoxImage](https://raw.githubusercontent.com/cdgriffith/Box/master/box_logo.png)](https://github.com/cdgriffith/Box)

Python dictionaries with advanced dot notation access.

```python
from box import Box

movie_box = Box({
    "Robin Hood: Men in Tights": {
        "imdb_stars": 6.7,
        "length": 104,
        "stars": [ {"name": "Cary Elwes", "imdb": "nm0000144", "role": "Robin Hood"},
                   {"name": "Richard Lewis", "imdb": "nm0507659", "role": "Prince John"} ]
    }
})

movie_box.Robin_Hood_Men_in_Tights.imdb_stars
# 6.7

movie_box.Robin_Hood_Men_in_Tights.stars[0].name
# 'Cary Elwes'
```
Box will automatically make otherwise inaccessible keys ("Robin Hood:
Men in Tights") safe to access as an attribute. You can always pass
`conversion_box=False` to `Box` to disable that
behavior.

Also, all new dict and lists added to a Box or BoxList object are
converted automatically.

```python
movie_box.Robin_Hood_Men_in_Tights.stars.append(
     {"name": "Roger Rees", "imdb": "nm0715953", "role": "Sheriff of Rottingham"})

movie_box.Robin_Hood_Men_in_Tights.stars[-1].role
# 'Sheriff of Rottingham'
```

## Install

```bash
pip install --upgrade python-box
```

Box 4 is tested on python 3.6+

If you have any issues please open a github issue with the error you are
experiencing!
