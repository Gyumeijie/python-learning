## Add search path for module with *sys.path*
> The built-in sys module has a list called `sys.path` that holds a list of the directories that constitute the `Python
path`.

- Add relative path
```python
import sys
sys.path.append('../../')
from importable import object1, object2, ... objectN
```

- Add absolute path
```python
import sys
sys.path.append('/home/work_dir')
from importable import object1, object2, ... objectN
```
