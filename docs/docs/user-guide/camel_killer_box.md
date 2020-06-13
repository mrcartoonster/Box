Similar to how conversion box works, allow CamelCaseKeys to be found as
snake_case_attributes.

``` {.python}
cameled = Box(BadHabit="I just can't stop!", camel_killer_box=True)

cameled.bad_habit
# "I just can't stop!"
```
