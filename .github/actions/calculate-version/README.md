# Calculate Version GitHub Action

This GitHub Action calculates the next version of your repository based on the commits and optionally creates a tag for it.

## Inputs

- `create_tag` (required): Indicates whether to create a tag for the new version.
- `branch` (required): Specifies the branch of the repository to base the version calculation on.

## Outputs

- `version`: The next calculated version based on the commit history.

## How It Works

1. **Checkout**: The action checks out the repository using the `actions/checkout@v4` action. It fetches the entire history of the repository to ensure accurate version calculation.
2. **Calculate Version**: The action then uses the `bitshifted/git-auto-semver@v1` action to calculate the next semantic version based on the commit messages. It takes the `main_branch` and `create_tag` inputs to determine how to perform the calculation and whether to tag the commit.