# Versioning

We use semantic versioning according to the following guide: https://semver.org/

In particular, we use the following tools  and guides to achieve this:

* [Poetry](https://python-poetry.org/) for dependency management and builds.
* [Python Semantic Release (PSR)](https://python-semantic-release.readthedocs.io/en/latest/) for resolving version number via commit messages.
* [Angular-style Commit Messages](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#commit-message-format) for version update commit message formatting
* [Angular-style Types](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#type) for versioning types

## Versioning with the Team

In order to get an accurate version number in a team with little oversight, we use `PSR` to bump the version number based on commit history. 

When finishing up the work on your branch, use a formatted commit message to tell `PSR` to bump the version:

```console
% git commit -a -m "fix(routes): Fixed the Route init bug"
```

This let's `PSR` know to bump the current patch version i.e. 0.1.2 -> 0.1.3.

See the `Angular-style` links up top for more detail.

## Example: Version :arrow_right: Build :arrow_right: Release Workflow

```console
% poetry add numpy  # Add numpy as a required package
% poetry add --dev black  # Add black as a dev-only package
% git commit -a -m "feature(packages): added numpy and black"  # Add a formatted commit message to inform PSR to bump the version
% semantic-release version  # Change the version number in pyproject.toml (based on commit history)
% poetry export --without-hashes --output requirements.txt  # Create a requirments.txt file to be used by deployment pipelines like P1
$ poetry2setup > setup.py  # Create setup.py file to be used by deployment pipelines
% poetry build  # Build our package for standard release
% git commit -a -m "Ran build"  # Commit the build binaries
% git push  # Push the new build to the repo
```

### Notes on our release workflow 

Our package releases are non-standard and require that we provide up-to-date `requirements.txt` and `setup.py` files. These files are used by deployment pipelines (i.e. Platform One) to build our package from source and deploy to a private repository.

In other words, we build the package for use in other BrainGu projects, but we provide standard files for our package to be built in a pipeline as well.

We like this guide and have based some decisions off of it https://py-pkgs.org/