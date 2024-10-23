# actions

Actions to simplify GitHub Actions workflows.

## Actions

- `setup-node-env`: Setups up Node, restores NPM cache and installs dependencies
- `publish-to-npm`: Sets up Node, runs the prepublishOnly script and publishes the package to the NPM registry

## Usage

To use an action in this repository, use it in a workflow job step:

```yml
# .github/workflows/example.yml

jobs:
  job:
    steps:
      # Uses the default branch
      - uses: bloq/actions/setup-node-env@master
      # Uses a specific version tag
      - uses: bloq/actions/setup-node-env@v1.0.0
```

See the GitHub Actions docs for details about [how to use a public action](https://docs.github.com/en/actions/writing-workflows/workflow-syntax-for-github-actions#example-using-a-public-action).
