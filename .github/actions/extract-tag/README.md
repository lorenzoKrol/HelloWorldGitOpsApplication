# Extract Tag Test GitHub Action

This GitHub Action extracts the previous tag from the repository and outputs it for further use.

## Outputs

- `tag`: The current tag of the application.

## How It Works

1. **Checkout code**: The action checks out the repository code using the `actions/checkout@v3` action, fetching the entire history to ensure all necessary files are available for extracting the tag.
2. **Get Previous Tag**: The action uses the `WyriHaximus/github-action-get-previous-tag@v1` action to extract the previous tag from the repository.
3.  **Output tag**: The action sets the `tag` output with the value of the extracted tag, making it available for further use.