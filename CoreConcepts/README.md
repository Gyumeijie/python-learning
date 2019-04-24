# Introduction
Recoding some core concepts of Python.

## Parameters vs Arguments
**Parameter**: A parameter is the variable which is part of the method’s signature, namely `method declaration`.

**Argument**: An argument is an expression used when `calling the method`.

There are two kinds of argument:

1. **keyword argument**: an argument preceded by an identifier (e.g. name=) in a function call or passed as a value in a dictionary preceded by \*\*. For example, 3 and 5 are both keyword arguments in the following calls to complex():

```python
 complex(real=3, imag=5)
 complex(**{'real': 3, 'imag': 5})
```

2. **positional argument**: an argument that is not a keyword argument. Positional arguments can appear at the beginning of an argument list and/or be passed as elements of an iterable preceded by \*. For example, 3 and 5 are both positional arguments in the following calls:

```python
 complex(3, 5)
 complex(*(3, 5)
```
