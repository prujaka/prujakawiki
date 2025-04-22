Environment:

```zsh
pyenv virtualenv 3.10.6 env_name
pyenv local env_name
pip install -r requirements.txt
```

Package:

```py
# setup.py
from setuptools import setup
from setuptools import find_packages

with open('requirements.txt') as f:
    content = f.readlines()
requirements = [x.strip() for x in content]

setup(name='package_name',
      version='0.0.1',
      description='Description',
      install_requires=requirements,
      packages=find_packages())
```

Install:

```zsh
pip install .
```

Check:

```zsh
pip freeze
```

Uninstall (move away from `setup.py`'s root to do it properly):

```zsh
pip uninstall package_name
```

Install for hot-reloading:

```zsh
pip install -e .
```

You can rerun this after updating the requirements. For `ipython` notebooks include this:

```py
%load_ext autoreload
%autoreload 2
```

