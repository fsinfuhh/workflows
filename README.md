# Reusable workflow definitions

This repository contains [reusable workflows](https://docs.github.com/en/actions/using-workflows/reusing-workflows) for
GitHub Actions that bundle common tasks of our CI/CD pipeline.

The contained workflows are:

- [build_image.yml](.github/workflows/build_image.yml) which builds a container and pushes it to GitHub packages (or another registry).

- [check_pre_commit.yml](.github/workflows/check_pre_commit.yml) for checking whether all [pre-commit](https://pre-commit.com/) checks pass
  
- [deploy.yml](.github/workflows/deploy.yml) for setting the deployed image digest in our [ansible repository](https://git.mafiasi.de/Server-AG/ansible).

See the linked workflow definitions for the list of inputs that they expect.

## How To Use

To use one of the defined workflows, define the job in your repository like this.
Also refer to the [GitHub Reference](https://docs.github.com/en/actions/using-workflows/reusing-workflows#calling-a-reusable-workflow=) for calling reusable workflows. 

```yaml
# .github/workflows/my_awesome_workflow.yml
…
jobs:
  my-awesome-job:
    uses: fsinfuhh/workflows/.github/workflows/build_image.yml@main
    with:
      image_tag: v42.0.7
```
