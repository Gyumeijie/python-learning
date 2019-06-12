## Single Lone Underscore(_)

This is typically used in the following two cases:
 - Refer to the the ***result of the last executed statement*** in an interactive interpreter session.
 
 - As a ***throw-away*** name
 > a certain name is assigned but not intented to be used.
 
 ```python
 n = 10
 for _ in range(n):
    do_something()
 ```
 
## Single Underscore Before a Name(e.g. _somename)

A name prefixed with an underscore(e.g. _spam)should be treated as a **non-public** part of the API, whether it is a `function`, a `method` or a `data member`. 

It's kind of a **convention** so that the next person(or yourself) using your code knows that a name starting with **_** is only for internal use.

By kind of a convention, I mean it actually does mean something to the interpreter. if you use `from 'module/package' import *`, then none of the names that start with a **_** will be imported, unless the module/package's **__all__** list contains them.

```python
__all__ = ["__nameone","__nametwo"] 
```

## Double Underscore Before a Name(e.g. __somename)

The use of double underscore in front of a name(specifically a method name) is not a convention; It has specific meaning to the interpreter.

Python **mangles** these names and it is used to avoid naming clases with those defined by subclasses.

Take the following example:

``` python
>>> class A(object):
...     def _internal_use(self):
...         pass
...     def __method_name(self):
...         pass
... 
>>> dir(A())
['_A__method_name', ..., '_internal_use']
```

```python
>>> class B(A):
...     def __method_name(self):
...         pass
... 
>>> dir(B())
['_A__method_name', '_B__method_name', ..., '_internal_use']
```

As expected, `_internal_use` doesn't change but the `__method_name` in both class is mangled to `_ClassName__method_name`


## Double Underscore Before and After a Name(e.g. __init__)

These are `special method names` used by Python. It is just a **convention**, a way for the Python system to use names that won't conflict with user-defined names.

There's nothing to stop you from writing your own special-method-looking name(but please don't):

```python
>>> class C(object):
...     def __mine__(self):
...         pass
...
>>> dir(C)
... [..., '__mine__', ...]
```

And it is easier to stay away from this type of naming and let only Python-defined special names follow the convention.
