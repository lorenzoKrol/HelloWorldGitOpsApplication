# Push Image GitHub Action

This GitHub Action pushes a Docker image to Docker Hub.

## Inputs

- `image_name` (required): Name of the image that is going to be pushed.
- `image_repository_username` (required): The username of the Docker account.
- `image_repository_password` (required): The password of the Docker account.
- `image_version` (required): Version of the image that is going to be pushed.

## How It Works

1. **Checkout**: The action checks out the repository code using the `actions/checkout@v4` action.
2. **Login to Docker Hub**: The action logs into Docker Hub using the `docker/login-action@v3` action with the provided Docker credentials.
3. **Set up Docker Buildx**: The action sets up Docker Buildx using the `docker/setup-buildx-action@v3.3.0` action, enabling advanced build capabilities.
4. **Push Docker Image**: The action uses the `docker/build-push-action@v5` action to build and push the Docker image to Docker Hub. It specifies the context as the current directory, the Dockerfile to use for building, and the image repository username, image name, and version for tagging and pushing.