# actions

Actions and workflows to make GitHub Actions simpler, more robust and more efficient.

## Actions

- `notify-deploy-to-slack`: Sends a notification to Slack using a pre-configured webhook.
- `publish-to-npm`: Sets up Node, runs the prepublishOnly script and publishes the package to the NPM registry.
- `setup-node-env`: Setups up Node, restores NPM cache and installs dependencies.

## Reusable workflows

- `js-checks`: Run standard checks as linter, code formatter; then run tests against different Node versions.
- `npm-publish`: Publish a package to NPM.

## Usage

To use the actions and workflows in this repository, add a reference as follows:

```yml
# .github/workflows/example.yml

jobs:
  job-one:
    steps:
      # Uses the default branch
      - uses: bloq/actions/setup-node-env@master
      # Uses a specific version tag
      - uses: bloq/actions/setup-node-env@v1.0.0
  job-two:
    uses: bloq/.github/workflows/js-checks.yml@v1
```

See the GitHub Actions docs for details about [how to use a public action](https://docs.github.com/en/actions/writing-workflows/workflow-syntax-for-github-actions#example-using-a-public-action) and how to reference a [reusable workflow](https://docs.github.com/en/actions/writing-workflows/workflow-syntax-for-github-actions#jobsjob_iduses).

## Release process

Once the PRs with the changes are approved, either merge the branch locally and push `master` or merge the PR in GitHub and pull `master`. Then update and push the tags:

```sh
./bump-version <major, minor, patch>
```
