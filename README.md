buildkite-agent Genesis Kit
===========================

This Genesis Kit lets you deploy a [Buildkite CI/CD][bk] agent to
your BOSH infrastructure, with ease.

Quick Start
-----------

To use it, you don't even need to clone this repository! Just run
the following (using Genesis v2):

```
# create a buildkite-agent-deployments repo using the latest version of the buildkite-agent kit
genesis init --kit buildkite-agent

# create a buildkite-agent-deployments repo using v1.1.0 of the buildkite-agent kit
genesis init --kit buildkite-agent/1.1.0

# create a my-buildkite-agent-configs repo using the latest version of the buildkite-agent kit
genesis init --kit buildkite-agent -d my-buildkite-agent-configs
```

Once created, refer to the deployment repository README for information on
provisioning and deploying new environments.

Features
-------

This kit currently has no optional features.

Params
------

The following parameters are supported:

- **instances** - How many instances to spin.  Defaults to 1.

- **network** - The network to put the Buildkite agent VMs in.
  Defaults to `network`.

- **vm_type** - The type of VM (from your Cloud Config) for the
  Buildkite Agent.  Defaults to `default`,

- **aws_access_key** - Your Amazon AWS Access Key ID (AKI).

- **aws-secret_key** - Your Amazon AWS Secret Access Key,

- **aws_region** - The Amazon AWS Region you want to operate in.

- **buildkite_token** - The Buildkite API token for authenticing
  your agent to your Buildkite account.

- **agent_environment** - A bash script (can be multi-line YAML)
  to execute before each run to set up the agent environment.

- **agent_tags** - A list of `key=value` tags to set on this
  Buildkite Agent during registration.  If not set, defaults to
  `queue=default` and `docker-available`.  If you want to _add_ to
  these tags, you will have to specify them explicitly when
  setting this parameter.

Cloud Config
------------

There is only one VM type in this deployment, which defaults to
`default` (in the `default` network).   That should be sized based
on the workloads you intend to run via Buildkite.

[bk]: https://buildkite.com/
