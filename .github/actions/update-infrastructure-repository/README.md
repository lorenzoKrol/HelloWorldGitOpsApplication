# Update Infrastructure Repository GitHub Action

This GitHub Action updates the Helm template in the infrastructure repository with the specified image version and commits the changes.

## Inputs

- `environment` (required): The target environment for the deployment.
- `github_infra_repo_username` (required): The username where the infrastructure repository is registered to.
- `github_infra_repo_name` (required): The name of the infrastructure repository.
- `github_application_repo_commit_username` (required): The username of the account you want to commit with to the infrastructure repository.
- `github_application_repo_commit_user_email` (required): The email of the account you want to commit with to the infrastructure repository.
- `github_access_token` (required): Authorization token.
- `image_version` (required): Version of the image that is going to be pushed.

## How It Works

1. **Checkout Code**: The action checks out the code from the infrastructure repository using the `actions/checkout@v4` action with the provided GitHub access token.
2. **Update Image Tag in values.yaml**: The action updates the image tag, version, and appVersion in the `values.yaml` and `Chart.yaml` files located in the Helm chart directory for the specified environment.
3. **Commit and Push Changes**: The action creates a new branch, commits the changes with the updated image version, and pushes the branch to the remote repository. It then creates a pull request to merge the changes into the `main` branch.