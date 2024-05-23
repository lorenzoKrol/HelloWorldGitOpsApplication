# Load Environment Variables GitHub Action

This GitHub Action loads environment variables from a specified .env file and outputs them for use in subsequent steps of the workflow.

## Inputs

- `path` (required): Path to the .env file.
- `mode` (optional): Mode for loading the .env file. Default is 'development'.

## Outputs

- `environment`: The target environment for the deployment.
- `github_infra_repo_username`: The username where the infrastructure repository is registered to.
- `github_infra_repo_name`: The name of the infrastructure repository.
- `github_application_repo_commit_username`: The username of the account you want to commit with to the infrastructure repository.
- `github_application_repo_commit_user_email`: The email of the account you want to commit with to the infrastructure repository.
- `dora_metrics`: If you want to generate DORA metrics. Values: TRUE||FALSE.
- `image_name`: Name of the image you want to build.
- `original_image_repository`: Name of the repository where the image is going to be promoted from.
- `target_image_repository`: Name of the repository where the image is going to be promoted to.

## How It Works

1. **Checkout**: The action checks out the repository code using the `actions/checkout@v4` action.
2. **Load .env file**: The action uses the `xom9ikk/dotenv@v2` action to load environment variables from the specified .env file.
3. **Output variables**: The action outputs the loaded environment variables according to the specified mode. For 'development' mode, it outputs variables related to image building. For 'acceptance' or 'production' mode, it outputs variables related to image promotion.