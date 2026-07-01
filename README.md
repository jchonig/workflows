# workflows

Public reusable GitHub Actions workflows for jchonig repositories.

## Workflows

### docker-build

Builds and pushes a Docker image to both GitHub Container Registry (ghcr.io) and Docker Hub.

**Usage:**

```yaml
jobs:
  build:
    uses: jchonig/workflows/.github/workflows/docker-build.yml@main
    with:
      image_name: myimage
    secrets:
      DOCKERHUB_USERNAME: ${{ secrets.DOCKERHUB_USERNAME }}
      DOCKERHUB_TOKEN: ${{ secrets.DOCKERHUB_TOKEN }}
```

**Inputs:**

| Name | Required | Description |
|------|----------|-------------|
| `image_name` | yes | Docker image name (e.g. `postfix`, `bind9`) |

**Secrets:**

| Name | Required | Description |
|------|----------|-------------|
| `DOCKERHUB_USERNAME` | yes | Docker Hub username |
| `DOCKERHUB_TOKEN` | yes | Docker Hub access token |

The workflow pushes to `ghcr.io/jchonig/<image_name>` and `jchonig/<image_name>`.
