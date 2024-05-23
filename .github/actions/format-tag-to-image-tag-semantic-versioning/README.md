# Format Extracted Tag GitHub Action

This GitHub Action formats an extracted tag to the image tag format.

## Inputs

- `tag_to_format` (required): The tag to format.

## Outputs

- `tag`: The formatted tag.

## How It Works

1. **Format Tag**: The action extracts the value of the `tag_to_format` input and formats it to the image tag format by removing the initial 'v' character if present.
2. **Output Tag**: The action sets the `tag` output with the formatted tag value, making it available for further use.