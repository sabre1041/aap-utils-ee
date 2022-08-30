# aap-utils-ee

Utilities to support the deployment and management of Ansible Automation Platform within an Execution Environment

## Setup

Since this Execution Environment is making use of certified content from Red Hat, ensure that the following steps have been configured.

* Authentication to the Red Hat Container Registry within the configured container runtime (Docker/Podman)
* A token to Automation Hub

A template _ansible.cfg_ file is available to simplify the configurations necessary to authenticate to Automation Hub.

Obtain an API token and export an environment variable:

```shell
export TOKEN=<AUTOMATION_HUB_TOKEN>
```

Generate _ansible.cfg_ file:

```shell
envsubst < ansible.cfg.template > ansible.cfg
```

## Build the Execution Environment

Execute the following command to build the Execution Environment:

```shell
ansible-navigator builder build -t <TAG>
```

## Push the Execution to an Image Registry (Optional)

Once the Execution Environment has been created, publish the Execution Environment to an image registry
