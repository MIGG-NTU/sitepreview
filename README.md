# sitepreview

![GitHub repo size](https://img.shields.io/github/repo-size/MIGG-NTU/sitepreview)
[![Clean up](https://github.com/MIGG-NTU/sitepreview/actions/workflows/cleanup.yaml/badge.svg)](https://github.com/MIGG-NTU/sitepreview/actions/workflows/cleanup.yaml)

The `gh-pages` branch of this repository hosts the documentation from PRs
of other repositories, so that we can preview the changes in PRs.

## How it works

The [`preview-pr.yml`](https://github.com/MIGG-NTU/MIG_Docs/blob/main/.github/workflows/preview-pr.yml)
workflow is triggered in PRs. It builds and pushes the documentation to the
to the `gh-pages` branch of this repository, and creates/updates a comment
with the preview URL link.

The URL scheme is:

    https://migg-ntu.github.io/sitepreview/MIGG-NTU/<repository_name>/<PR_branch_name>

## Cleanup

The [workflow](.github/workflows/cleanup.yaml) runs daily to:

1. Delete the documentation if the corresponding branch was already deleted
2. Generate an index file, which lists all documentations of current open PRs
3. Squash all commits into one commit to avoid increasing repository size

## Acknowledgemnt

The repository is modified from https://github.com/seismo-learn/sitepreview.
