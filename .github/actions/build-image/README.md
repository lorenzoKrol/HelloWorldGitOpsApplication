# Build Image GitHub Action

This GitHub Action builds a Docker image from the specified Dockerfile and optionally pushes it to an image repository.

## Inputs

- `image_repository_username` (required): The username of the image repository account.
- `image_repository_password` (required): The password of the image repository account.

## How It Works

1. **Checkout**: The action checks out the repository using the `actions/checkout@v4` action, fetching the entire history to ensure all necessary files are available for building the Docker image.
2. **Login to Image Repository**: The action logs into the specified image repository using the `docker/login-action@v3` action with the provided credentials.
3. **Set up Docker Buildx**: The action sets up Docker Buildx using the `docker/setup-buildx-action@v3.3.0` action, allowing for advanced build capabilities.
4. **Build Docker Image**: The action builds the Docker image from the `Dockerfile` in the repository using the `docker/build-push-action@v5` action. By default, the image is not pushed to the image repository (`push: false`).