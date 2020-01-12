## scope resolutuion in python | LEGB rule

**Namespaces** : A namespace is a `container` where names are `mapped` to objects, they are used to avoid confusions in cases where same names exist in different namespaces. They are created by modules, functions, classes etc.

**Scope** : A scope defines `the hierarchical order` in which the namespaces have to be `searched` in order to obtain the mappings of name-to-object(variables). It is a context in which variables exist and from which they are referenced. It defines the accessibility and the lifetime of a variable.

### Scope resolution via LEGB rule

In Python, the `LEGB` rule is used to decide the order in which the namespaces are to be searched for scope resolution.
The scopes are listed below in terms of hierarchy(highest to lowest/narrowest to broadest):

- Local(L): Defined inside function/class
- Enclosed(E): Defined inside enclosing functions(Nested function concept)
- Global(G): Defined at the uppermost level
- Built-in(B): Reserved names in Python builtin modules


### Python has not block scope
> In c++/c/java, a block is a scope

```python
for i in range(3):
    if i == 0:
        sum = 0
    else:
        sum += i
print(sum) # sum is still visible outside the for block
```
