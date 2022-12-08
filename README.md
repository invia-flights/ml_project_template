# Template project

## To-dos to setup a new project
1. run `brew bundle install`
2. run `poetry install`
3. run `pre-commit install`
4. run `nbstripout --install`
5. run `dvc init`
5. Adjust the `.dvc/config` to something like this:
```
[core]
    remote = storage
    autostage = true
['remote "storage"']
    url = s3://[PROJECT-S3-BUCKET]/dvcstore
```
6. Adjust `dvc.yaml`. In most cases, you just have to adjust `cmd: python src/train.py` to something suitable for your project.
7. Adjust `params.yaml`. Probably you want to leave it empty until you run your first experiment.
8. Adjust `pyproject.toml` (`name`, `description`, `authors`, etc.)
9. Install your dependencies (e.g. `poetry add pandas==1.5.2`)
10. Run `dvc commit` and just ignore all warnings and error for now.

## Things to remember
* Notebooks and code for research should be placed in a `research` folder.
* Data should be placed in a `data` folder.
* Models should be placed in a `models` folder.
* Production code should be placed in a `src` folder.
* Tests should be placed in a `tests` folder.
* Don't ignore what `pylint` and `mypy` tell you.
