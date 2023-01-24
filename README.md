# NeIC AHM23 Releasing a Python Package with CI

Demo on how to release a python package with CI and Github Workflows using Twine and Tox.

- Creating and uploading a Python package as part of the CI workflow
- The choice between `setup.py` vs `pyproject.toml` vs `setup.cfg`. Do I need 3 files with the latest version of python? 
   - PyPI vs test-PyPI vs pip installing from GitHub
- Securing a python package

#### Discussion points

- How would this differ on GitLab?
- What about poetry?
- Testing and coverage.


### Future work (help wanted)

- Publishing docs with github actions along side publishing 


### Installing 

The project can be install through cloning the github repo and `pip install .` in the repo root directory. For an editable install you can use `pip install -e .`. For the dev build (twine, tox, wheel) you can use `pip install .[dev]`. 


### Publishing

In this project when you push to `CHANGELOG.rst`, this triggers the `tag_and_release` workflow. Creating a tag via `git tag -l` and running the `tag-from-pipeline.sh` bash script. Once a tag has been created this workflow triggers the `publish.yml` workflow, publishing the package to PyPI. 

What you will need in your own projects should you wish to fork is two secrets. In your repositories settings > Secrets and variables > Actions add the following secrets:

```
PYPI_USER
PYPI_PASSWORD
```
- Tag and Release 
- Publish to PyPI 

### How to make this package secure and publishing securely?

This package is by no means secure. 

- Signed commits and good secure git practices
- Use PyPI API tokens and PyPI 2FA
- Use dependabot to check for security issues in dependencies
- Protected branches and setup Github rules
- Protect your tags
- Create a new GitHub environment for publishing 
- Private vulnerablity reporting 

It is also, always good practice to verify reproducible builds. 
- Build locally and verify checksums:

```
sha256sum dist/*.whl
``` 