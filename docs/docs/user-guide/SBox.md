Shorthand Box, aka SBox for short(hand), has the properties
`json`, `yaml` and `dict` for faster
access than the regular `to_dict()` and so on.

```python
from box import SBox

sb = SBox(test=True)
sb.json
# '{"test": true}'
```

Note that in this case, `json` has no default indent, unlike
`to_json`.title-ref}.
