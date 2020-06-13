A Box with additional handling of string manipulation generally found in
config files.

test_config.ini

```ini
[General]
example=A regular string

[Examples]
my_bool=yes
anint=234
exampleList=234,123,234,543
floatly=4.4
```

With the combination of `reusables` and
`ConfigBox` you can easily read python config values into
python types. It supports `list`, `bool`,
`int` and `float`.

```python
import reusables
from box import ConfigBox

config = ConfigBox(reusables.config_dict("test_config.ini"))
# <ConfigBox: {'General': {'example': 'A regular string'},
# 'Examples': {'my_bool': 'yes', 'anint': '234', 'examplelist': '234,123,234,543', 'floatly': '4.4'}}>

config.Examples.list('examplelist')
# ['234', '123', '234', '543']

config.Examples.float('floatly')
# 4.4
```
