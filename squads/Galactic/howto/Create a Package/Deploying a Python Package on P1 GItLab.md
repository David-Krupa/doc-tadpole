# Deploying a Python Package on Platform One GitLab

## Purpose :brain:

Learn how to deploy and use your Python package on Platform One GitLab from release to `pip install`.

## Tooling :wrench:

- [Poetry](https://python-poetry.org/): Used for dependency management and painless builds. Can export our `requirements.txt` file
- [poetry2setup](https://pypi.org/project/poetry2setup/): Converts our `pyproject.toml` file to `setup.py`

## Project Preparation :memo:

We need to make sure that `setup.py` and `requirements.txt` are included in our repo so that the P1 pipeline can build our package from source. We can do this with `poetry` and `poetry2setup`:

```console
% poetry2setup > setup.py  # creates our setup.py from pyproject.toml
% poetry export --without-hashes --output requirements.txt  # Exports our dependencies in pyproject.toml as a standard requirements.txt file
```

Additionally, make sure you do not include the `build` and `dist` directories if you are are using the GitHub `mirror` technique to push changes to this project. The pipeline will take care of `build` and `dist` when deploying the package.

:star:Don't forget to add and push changes!:star:

## Request a P1 Package Pipeline :new:

You'll need to request a `Package Pipeline` from [Platform One Help Center P1 Customer App Support](https://jira.il2.dso.mil/servicedesk/customer/portal/73) using the `New Pipeline Request` type.

Here is a good example of info required for this request:

```
Description
Hello,
I am requesting a new package pipeline for the https://code.il2.dso.mil/platform-one/products/widow/widow-components repository.

The command "npm run build:ci" in package.json needs to added before the "before_script" in order to build the package

Gitlab Repo
https://code.il2.dso.mil/platform-one/products/widow/widow-components

Who is your sponsor?
ABMS
```

## Build and Release :package:

Once your pipeline is active, run a pipeline for your `main`/`master` branch at `/-/pipelines` or by selecting `Pipelines` from the `CI/CD` tab in the side bar.

You'll have to manually release the package after pipeline completes.

We can check for release at `/-/packages` or by selecting `Package Registry` in the left bar.

### Troubleshooting Package Releases

  Problem: `publish package` step results in `ERROR` and logs `HTTPError: 400 Bad Request...`
  - Possible Solution: You are accidentally attempting to overwrite a package version. If version `1.1.0` already exists in the Package Registry and you build and publish `1.1.0` again, you will receive this error.

## Install Your Package :truck:

Now we can test our package install. On another P1 GitLab Python project, add the following to the top of the `requirements.txt` file:

```txt
--extra-index-url "https://'<token_name>':<token>@code.il2.dso.mil/api/v4/projects/<project_id>/package/pypi/simple"
...
```

Where:
- `token_name`: The name of the access token you created for your project in `/settings/access_tokens` (i.e. GitHub Push Access)
- `token`: The token you saved locally on creation at `/settings/access_tokens`
- `project_id`: Your Project ID located under the project name on your GitLab repo home page
  
NOTE: For now, we have to expose the token. We should look into a way is more secure.

Next, we can add our package by name with the specified version as usual in `requirements.txt`:

```txt
...
braingu-some-package==1.1.0
```