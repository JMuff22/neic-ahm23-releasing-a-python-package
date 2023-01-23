# NeIC AHM23 Releasing a Python Package with CI

Demo on how to release a python package with CI and Github Workflows using Twine and Tox.

- Creating and uploading a Python package as part of the CI workflow
- The choice between `setup.py` vs `pyproject.toml` vs `setup.cfg`. Do I need 3 files with the latest version of python? 
   - pytest vs unittest and integration with CI
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

- Tag and Release 
- Publish to PyPI 