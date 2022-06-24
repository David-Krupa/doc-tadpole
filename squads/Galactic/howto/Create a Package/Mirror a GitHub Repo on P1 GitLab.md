# How to Mirror a GitHub Repo on P1 GitLab

## Purpose :brain:

Learn how to auto-push code from a BrainGu private repository straight to Platform One GitLab mirrored respository.

NOTE: Here `mirror` means that the repository receives the commit history of the `original` project (with some extra commits depending on your GitHub Actions). The `mirror` is essentially a source code clone to be built on a separate platform (i.e. Platform One)

## Create `mirror` GitLab project and repository :new:

Contact Matt Shaver to create a repository for the `mirror` project on Platform One GitLab. It should be empty.

## Create GitLab Access Token :closed_lock_with_key:

In `/settings/access_tokens` of the `mirror` project, create and save (locally) an access token with the following attributes (json used here for sake of formatting):

```json
{
    "Token name": "GitHub Push Access",
    "Scopes": [
        "api", 
        "read_api", 
        "read_repository",
        "write_repository",
        "read_registry", 
        "write_registry"
    ],
    "Expires": "Never",
    "Role": "Maintainer"
}
```

## Add `gitlab-mirroring.sh` :page_facing_up:

In the `original` GitHub repo, add the following script to your project:

```sh

git remote add target https://${INPUT_TARGET_USERNAME}:${INPUT_TARGET_TOKEN}@${INPUT_TARGET_URL#https://}

git pull target ${GITHUB_REF##*/}

case "${GITHUB_EVENT_NAME}" in
  push)
    git push --all --force target
    git push --tags --force target
    ;;
  delete)
    git push -d target ${GITHUB_EVENT_REF}
    ;;
  *)
    ;;
esac
```

This script tells GitHub to start pushing/deleting code for each push that comes into the repo going forward.

## Add `gitlab-mirroring.yml` :memo:

We need to add config files for GitHub which will be in the following directory:

```
project_root_directory
|
|__ .github
    |
    |__ workflows
        |- gitlab-mirroring.yml
```

`gitlab-mirroring.yml`:

```sh
name: Gitlab Mirroring

on:
  - push
  - delete

jobs:
  sync:
    runs-on: ubuntu-latest
    env:
      INPUT_TARGET_URL: ${{ secrets.GITLAB_REPO_URL }}
      INPUT_TARGET_USERNAME: ${{ secrets.GITLAB_USER_NAME }}
      INPUT_TARGET_TOKEN: ${{ secrets.GITLAB_ACCESS_TOKEN }}
      GITHUB_EVENT_REF: ${{ github.event.ref }}
    name: Git Repo Sync
    steps:
      - uses: actions/checkout@v2
        with:
          fetch-depth: 0
      - name: Remove Github Actions folder
        run: rm -rf .github
      - name: Build project
        run: |
          python setup.py -q sdist bdist_wheel
      - name: Remove build folder
        run: rm -rf build
      - name : Remove dist folder
        run: rm -rf dist
      - name: Commit new Build
        run: |
          git config pull.rebase false
          git config --global user.name "Some Person"
          git config --global user.email "some.person@braingu.com"
          git add .
          git commit -m 'add build files in dist directory'
      - name: Sync Repos
        run: sh ./gitlab-mirroring.sh
```

NOTE: For this script/example, a `python` build step was used. You will have to supplement your own commands here as these define the GitHub Actions.

## Add Actions secrets :key:

In GitHub, go to `/settings/secrets/actions` for your `original` project. You'll need to add 3 secrets to match the variables used in our `.yml` file:

- `GITLAB_ACCESS_TOKEN`: The generated token from [Create GitLab Access Token :closed_lock_with_key:](#create-gitlab-access-token-)
- `GITLAB_REPO_URL`: The url for the `mirror` project from [Create `mirror` GitLab project and repository :new:](#create-mirror-gitlab-project-and-repository-)
- `GITLAB_USER_NAME`: A GitLab username that has access to the project (likely your own)

## Test the setup :rocket:

Push a new commit from a branch to test the setup. You should see a workflow in `/actions` on GitHub that matches your commit message.

Back in GitLab, you should now see the branch your pushed too with the complete repository codebase.
