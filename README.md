# Scikit-HEP: cookie

[![Actions Status][actions-badge]][actions-link]
[![Code style: black][black-badge]][black-link]

[![GitHub Discussion][github-discussions-badge]][github-discussions-link]
[![Gitter][gitter-badge]][gitter-link]
[![Scikit-HEP][sk-badge]](https://scikit-hep.org/)

A cookiecutter template for new Python projects, designed off of the
[Scikit-HEP developer guidelines][]. Template generation testing with GitHub
Actions.

Be sure you have read the [Scikit-HEP developer guidelines][] first, and
possibly used them on a project or two first. This is _not_ a minimal example
or tutorial. It is a collection of useful tooling for starting a new project
using cookiecutter, or for copying in individual files for an existing project
(by hand, from `{{cookiecutter.project_name}}/`).

This is a pure python template project, with the following project types:

1. Setuptools: the classic build system.
2. Pybind11: This is setuptools but with an C++ extension written in pybind11.
3. Flit: A modern, lightweight build system for pure Python projects. Replaces
   setuptools, no MANIFEST.in, setup.py, sometimes no setup.cfg (flake8 and
   MyPy still require it). Low learning curve.
4. Poetry: An all-in-one solution to pure Python projects. Replaces setuptools,
   venv/pipenv, pip, wheel, and twine. Higher learning curve, but is
   all-in-one.

#### To use:

Install cookiecutter, ideally with `brew install cookiecutter` if you use brew,
otherwise with `pipx install cookiecutter`. Then run:


```bash
cookiecutter gh:scikit-hep/cookie
```

Answer all the questions. If you are not making a Scikit-HEP repo, just enter a
different org name.

Check _at least_ `setup.cfg`. Update README.md. Also update and add docs to `docs/`.

There are a few example dependencies and a minimum Python version of 3.6,
change to whatever you actually need/want.

#### Contained components:

* GitHub actions runs testing
    - Not using Tox because native testing is faster
* GitHub actions deploy
    - Be sure to add a token
* Dependabot keeps actions up to date periodically, through useful pull requests
* Formatting handled by pre-commit
    - No reason not to be strict on a new project
    - Includes MyPy - static typing
    - Includes strong Flake8 checking
    - Includes auto fixes for most flake8 problems
    - Includes Black
* A rough version of ReadTheDocs Sphinx docs provided

Setuptools only:

* Setuptools controlled by setup.cfg and a nominal setup.py.
    - Using declarative syntax avoids needless boilerplate that is often wrong (like incorrectly handling the encoding when opening a README).
    - Easier to adapt to PEP 621 eventually.
    - Any actually logic can sit in setup.py and be clearly separate from simple metadata.
* Versioning handled by `setuptools_scm`
    - You can easily switch to manual versioning, but this avoids duplicating the version as git tags and in the source, and versions _every_ commit uniquely, sidestepping some caching problems.

[actions-badge]:            https://github.com/scikit-hep/cookie/workflows/CI/badge.svg
[actions-link]:             https://github.com/scikit-hep/cookie/actions
[black-badge]:              https://img.shields.io/badge/code%20style-black-000000.svg
[black-link]:               https://github.com/psf/black
[conda-badge]:              https://img.shields.io/conda/vn/conda-forge/cookie
[conda-link]:               https://github.com/conda-forge/cookie-feedstock
[github-discussions-badge]: https://img.shields.io/static/v1?label=Discussions&message=Ask&color=blue&logo=github
[github-discussions-link]:  https://github.com/scikit-hep/cookie/discussions
[gitter-badge]:             https://badges.gitter.im/Scikit-HEP/community.svg
[gitter-link]:              https://gitter.im/Scikit-HEP/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge
[sk-badge]:                 https://scikit-hep.org/assets/images/Scikit--HEP-Project-blue.svg

[Scikit-HEP developer guidelines]: https://scikit-hep.org/developer
