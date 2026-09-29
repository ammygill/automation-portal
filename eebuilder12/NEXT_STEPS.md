# Next Steps

Complete the following setup to enable automated EE builds.

## Required Secrets

Configure these secrets in **Settings > Secrets and variables > Actions > New repository secret**.

### Galaxy Server Tokens

These tokens authenticate `ansible-galaxy collection install` during the EE build.

| Secret | Purpose |
|--------|---------|
| `ANSIBLE_GALAXY_SERVER_PRIVATE_HUB_RH_CERTIFIED_TOKEN` | Galaxy server authentication token |
| `ANSIBLE_GALAXY_SERVER_PRIVATE_HUB_VALIDATED_TOKEN` | Galaxy server authentication token |
| `ANSIBLE_GALAXY_SERVER_PRIVATE_HUB_PUBLISHED_TOKEN` | Galaxy server authentication token |

### SCM Tokens

These tokens authenticate `git clone` for private collection repositories.

| Secret | Purpose |
|--------|---------|
| `AAP_EE_BUILDER_GITHUB_GITHUB_PUBLIC_OPENTRAINING_LABS_CUSTOMIZATIONS_TOKEN` | Git access for collections from `github.com` |

## Optional Secrets

| Secret | Purpose |
|--------|---------|
| `REGISTRY_PASSWORD` | Container registry password (defaults to `GITHUB_TOKEN`) |
| `REDHAT_REGISTRY_PASSWORD` | Red Hat registry password (for pulling base images) |

## Repository Variables

Configure these in **Settings > Secrets and variables > Actions > Variables**.

| Variable | Default | Purpose |
|----------|---------|---------|
| `REGISTRY_USERNAME` | `github.actor` | Username for the container registry where the built image will be pushed (defaults to `github.actor`) |
| `EE_REGISTRY` | `aap-aap.apps.cluster-rmw6v.dyn.redhatworkshops.io` | Container registry hostname |
| `EE_IMAGE_NAME` | `<owner>/<repo>` | Image name |
| `REDHAT_REGISTRY_USERNAME` | - | Red Hat registry username |

## Verify Your Setup

1. Configure all required secrets listed above
2. Push to a branch or open a pull request to trigger the workflow
3. Check the workflow run in **Actions** for any authentication errors
4. Once the build succeeds, verify the image in your container registry
