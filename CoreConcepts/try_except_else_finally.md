## Take Advantage of Each Block in try/except/else/finally

The each block: try, except, else, and finally serves a unique purpose in the compound statement.
> The `else block` helps you minimize the amount of code in thetry block and improves readability

```python
dictionary = {"key" : "value"}
try:
    value = dictionary["key"]
except KeyError as e:
    print("except")
else:
    """
    The else block helps you minimize the amount of code in the
    try block and improves readability
    """
    print("else")
```
