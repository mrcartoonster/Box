`Box` is a subclass of `dict` and as such,
certain keys cannot be accessed via dot notation. This is because names
such as `keys` and `pop` have already been
declared as methods, so `Box` cannot use it's special sauce
to overwrite them. However it is still possible to have items with those
names in the `Box` and access them like a normal dictionary,
such as `my_box.['keys']`.

*This is as designed, and will not be changed.*

Common non-magic methods that exist in a `Box` are: `clear`,
`copy`, `from_json`, `fromkeys`, `get`, `items`, `keys`, `pop`, `popitem`, `setdefault`,
`to_dict`, `to_json`, `update`, `merge_update`, `values`. To view
an entire list of what cannot be accessed via dot notation, run the
command `dir(Box())`.


## Box's parameters

 |Keyword Argument    |Default     |Description
 |--------------------|:-----------|:------------------------------------------------------------------------------
 |conversion\_box     |True        |Automagically make keys with spaces attribute accessible
 |frozen\_box         |False       |Make the box immutable, hashable (if all items are non-mutable)
 |default\_box        |False       |Act like a recursive default dict
 |default\_box\_attr  |Box         |Can overwrite with a different (non-recursive) default attribute to return
 |camel\_killer\_box  |False       |CamelCaseKeys become attribute accessible like snake case (camel\_case\_keys)
 |box\_safe\_prefix   |"x"         |Character or prefix to prepend to otherwise invalid attributes
 |box\_duplicates     |"ignore"    |When conversion duplicates are spotted, either ignore, warn or error
 |box\_intact\_types  |()          |Tuple of objects to preserve and not convert to a Box object
 |box\_recast         |None        |cast certain keys to a specified type
 |box\_dots           |False       |Allow access to nested dicts by dots in key names

## Box's functions

 |Function Name  |Description
 |---------------|:-----------------------------------------------------------------------------------------------
 |to\_dict       |Recursively transform all Box (and BoxList) objects back into a dict (and lists)
 |to\_json       |Save Box object as a JSON string or write to a file with the [filename]{.title-ref} parameter
 |to\_yaml       |Save Box object as a YAML string or write to a file with the [filename]{.title-ref} parameter
 |to\_toml\*     |Save Box object as a TOML string or write to a file with the [filename]{.title-ref} parameter
 |from\_json     |Classmethod, Create a Box object from a JSON file or string (all Box parameters can be passed)
 |from\_yaml     |Classmethod, Create a Box object from a YAML file or string (all Box parameters can be passed)
 |from\_toml\*   |Classmethod, Create a Box object from a TOML file or string (all Box parameters can be passed)
 |merge\_update  |Recursively merge dictionaries or Boxes together instead of replacing

\* Do not work with `BoxList`, only `Box`
