All commands assume you have a virtual environment running already.

### Show dependency tree in a python project (must have `pipdeptree` installed)
Run `pipdeptree --local-only` to see only project dependencies, and their dependencies.

### Upgrade a python package
Upgrade an already installed `SomeProject` to the latest from PyPI, run `pip install -U SomeProject`.

### List which packages have updates available
`pip list --outdated`.
