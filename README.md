# Publishing Python packages to PyPI


## Gitignore
Ready-to-use .gitignore exemples

https://www.toptal.com/developers/gitignore

## License
https://choosealicense.com/


## Build with distribution

    python setup.py bdist_wheel sdist
    #bdist_wheel and sdist commands can be used separately too

## Install locally (for testing purposes)
    pip install -e .

## Make sure it works
    #whatever.py
    from special import hello

## Push to PyPi
    twine upload dist/*

Instead of being prompt for credentials, get a token in pypi's website (settings), and place `.pypirc` inside your #HOME folder, containing:

```
[pypi]
  username = __token__
  password = <token>

```
## CI/CD pipeline
### Versioning to PyPI
Use `python-package.yml` to create a new version on PyPi after creating a new release on github. (Make sure you updated the version on `setup.py` before doing so!). Also, place `PYPI_API_TOKEN` in git secrets.

### Testing
Use `python-package.yml` to run tests with `pytest` upon new commits to `master` branch.