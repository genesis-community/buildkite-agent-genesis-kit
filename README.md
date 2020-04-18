# buildkite-agent Genesis Kit

This Genesis Kit lets you deploy a [Buildkite CI/CD](https://buildkite.com/) agent to
your BOSH infrastructure, with ease.

## Quick Start

To use it, you don't even need to clone this repository! Just run
the following (using Genesis v2):

```plain
# create a buildkite-agent-deployments repo using the latest version of the buildkite-agent kit
genesis init --kit buildkite-agent

# create a buildkite-agent-deployments repo using v1.1.3 of the buildkite-agent kit
genesis init --kit buildkite-agent/1.1.3

# create a my-buildkite-agent-configs repo using the latest version of the buildkite-agent kit
genesis init --kit buildkite-agent -d my-buildkite-agent-configs
```

Once created, refer to the deployment repository README for information on
provisioning and deploying new environments.

## Development

This genesis kit uses upstream deployment manifests and operators from [buildkite-agent-boshrelease](https://github.com/starkandwayne/buildkite-agent-boshrelease). They are versioed and vendored inside `manifests/` folder.

To update with [vendir](https://github.com/k14s/vendir), bump `vendir.yml` and run `vendir sync`.
