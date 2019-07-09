# Decorator

**Decorators** are very powerful and useful tool in Python since it allows programmers to `modify the behavior` of ***function*** or ***class***. 

**Decorators** allow us to wrap another function in order to extend the behavior of wrapped function,   `without permanently modifying it`.

## Single decorator without arguments

```python
from functools import wraps

def decorator(func):
  @wraps(func)
  def wrapper(*args, **kwargs):
    # some actions here
    print('Decorator')
    return func(*args, **kwargs)
 return wrapper
```

```python
@decorator
def func(x, y):
  pass
```

The decoration process evaluates as follows:

```python
def func(x, y):
 pass
 
func = decorator(func)
```

## Single decorator takes arguments

```python
from functools import wraps

def decorator(x, y, z):
  def decorate(func):
    @wraps(func)
    def wrapper(*args, **kwargs):
      # some actions here
      print('Decorator')
      return func(*args, **kwargs)
   return wrapper
  return decorate
```

```python
@decorator(x, y, z)
  def func(a, b):
    pass
```

The decoration process evaluates as follows:

```python

def func(a, b):
 pass
 
func = decorator(x, y, z)(func)
```

## Multiple decorators

```python
from functools import wraps

def decorator1(func):
  @wraps(func)
  def wrapper(*args, **kwargs):
    # some actions here
    print('Decorator 1')
    return func(*args, **kwargs)
 return wrapper

def decorator2(func):
  @wraps(func)
  def wrapper(*args, **kwargs):
    # some actions here
    print('Decorator 2')
    return func(*args, **kwargs)
  return wrapper
 ```
 
```python
@decorator1
@decorator2
def add(x, y):
  return x + y
```
The decoration process evaluates as follows:

```python
def add(x, y):
  return x + y

add = decorator2(add)
add = decorator1(add)
```
