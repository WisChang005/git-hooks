# Git Hooks

## Pre-commit Installation
```
# clone this repository and install pre-commit hooks
# change directory

# Install pre-commit package
pip install -r requirements.txt

# verify and mondify .pre-commit-config.yaml for your python enviroment (default Python3.6)
notepad .pre-commit-config.yaml

# Install pre-commit to your repository
pre-commit install
```

## Skip Checker to Commit
Skip the rule checker `black` and `flake8` with the following command:
```
SKIP=black,flake8 git commit -m "commit info"
```

## Pre-commit contents
If you want to "skip", "ignore" or "add" the git hook rule, trying to modify pre-commit config file and take off the checker id in `.pre-commit-config.yaml` and run `pre-commit install` again.

>*[.pre-commit-config.yaml](.pre-commit-config.yaml) is pre-commit package install source file*

>*[.flake8](.flake8) file is flake8's config file, default max-line-length=120*

>*[black_config.toml](black_config.toml) file is black formatter config file, default line-length=120*

* black - Black is the uncompromising Python code formatter.
* flake8 - Run flake8 on your python files.
* check-ast - Simply check whether files parse as valid python.
* check-merge-conflict - Check for files that contain merge conflict strings.
* trailing-whitespace - Trims trailing whitespace.
* end-of-file-fixer - Makes sure files end in a newline and only a newline.

### Default Setting in `.pre-commit-config.yaml`
```
repos:
-   repo: https://github.com/ambv/black
    rev: stable
    hooks:
    - id: black
      language_version: python3.6 ##### [plase change python version for your environment] #####
-   repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v2.2.3
    hooks:
    - id: flake8
    - id: check-ast
    - id: check-merge-conflict
    - id: trailing-whitespace
    - id: end-of-file-fixer
```

## Reference
* [Python workflow using pre-commits](https://ljvmiranda921.github.io/notebook/2018/06/21/precommits-using-black-and-flake8/)
* [pre-commit](https://github.com/pre-commit/pre-commit-hooks)
* [pre-commit-introduction](https://pre-commit.com/#intro)
* [flake8](https://pypi.org/project/flake8/)
* [black](https://github.com/ambv/black)
