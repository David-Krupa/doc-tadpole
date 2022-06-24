# How to Create a Python Package

## Purpose :brain:

Learn how to create a Python Package on GitHub for use in BrainGu projects.

## Tooling :wrench:

- [Poetry](https://python-poetry.org/): Used for dependency management and painless builds. This requires that we use a [pyproject.toml](https://python-poetry.org/docs/pyproject/) file.
- [Python Semantic Versioning (PSR)](https://python-semantic-release.readthedocs.io/en/latest/): Resolves version through commit history
- [Angular-style commit message format](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#commit-message-format): `PSR`'s standard parser accepts these types of formatted messages

## Setup `poetry` in `pyproject.toml` :page_with_curl:

Using the [Poetry README.md](https://github.com/python-poetry/poetry) as a guide, install `Poetry` and enter in your project info in `pyproject.toml`. 

Example:

```toml
...
[tool.poetry]
name = "braingu_some_package"
version = "1.0.0"
description = "A generalized package."
authors = ["Some Person"]

[tool.poetry.dependencies]
python = "^3.8"
numpy = "1.21.1"
pytest = "6.2.4"

[tool.poetry.dev-dependencies]
black = "21.8b0"
coverage = "5.5"
```

NOTE: If you have not been using `Poetry`, you should add packages to your package via `poetry add` going forward. This will define packages in your `pyproject.toml` file for you.

## Setup `semantic_release` in `pyproject.toml` :memo:

First, add `python-semantic-release` via `poetry`:

```console
% poetry add --dev python-semantic-release
```

Then we need to point `PSR` to the `version` variable to resolve versioning through commit history.

Add the following:

```toml
[tool.semantic_release]
version_toml = "pyproject.toml:tool.poetry.version" 
```

## Commit a formatted message :bookmark:

We can now commit a feature to create a MINOR version bump in our commit history. See [Angular-style commit messages](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#commit-message-format)

```console
% git commit -a -m "feat(package): Added poetry setup and semantic versioning"
```

NOTE: Make sure you added `pyproject.toml` to your `git` repo.

Next run `PSR` to bump the version:

```console
% semantic-release version
```

Check that `version` in your `pyproject.toml` has bumped from `1.0.0` to `1.1.0`

## Build the package :package:

We're ready to build our version `1.1.0` package:

```console
% poetry build
```

You should see a `dist` directory with `.whl` and `.tar.gz` files matching your package name and version.

## Push and Test :truck:

Add the newly built binaries to your git repo and commit/push all changes.

In a separate package, you can add our new package in the `requirements.txt` file:

```txt
braingu-some-package @ git+ssh://git@github.com/braingu/some-package.git
```

Or you could do this via `pip install`, but be careful when freezing your requirements. It will attach a commit hash which may not be what you want.

```console
% pip install braingu-some-package@git+ssh://git@github.com/braingu/some-package.git
```

NOTE: Underscores (`_`) have been replaced with hyphens (`-`) on purpose.

NOTE: This usage implies that you have `ssh` for `github.com` setup properly.