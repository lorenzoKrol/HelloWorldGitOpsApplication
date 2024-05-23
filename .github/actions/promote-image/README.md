# Promote Image GitHub Action

This GitHub Action promotes a Docker image from one repository to another.

## Inputs

- `image_repository_username` (required): The username of the Docker account.
- `image_repository_password` (required): The password of the Docker account.
- `image_version` (required): Version of the image that is going to be promoted.
- `original_image_repository` (required): Name of the repository where the image is going to be promoted from.
- `target_image_repository` (required): Name of the repository where the image is going to be promoted to.

## How It Works

1. **Checkout**: The action checks out the repository code using the `actions/checkout@v4` action.
2. **Login to Docker Hub**: The action logs into Docker Hub using the `docker/login-action@v3` action with the provided Docker credentials.
3. **Pull and Push Image**: The action pulls the Docker image from the source registry, tags it with the target repository, and pushes it to the target registry.