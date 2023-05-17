# runZero Explorer Helm Chart

- [Requirements](#requirements)
- [Installing](#installing)
- [Configuration](#configuration)

## Requirements

* These items are required:
    * [Deploy a registry server](https://docs.docker.com/registry/deploying/)
    * Create a customized Docker image tagged for a specific runZero Organization (requires Ansible). Replace "REGISTRY_HOST" with the host name of the private Docker registry, "ORG" with a runZero Organization, and "UNIQUE_TOKEN" and "VERSION_ID" with values found by going to https://console.runzero.com/deploy/download/explorers and clicking on the "Linux Distributions" button. The URL is formatted like this: https://console.runzero.com/download/explorer/UNIQUE_TOKEN/VERSION_ID/runzero-explorer-linux-amd64.bin
    `ansible-playbook create-dockerfile.yml \
		-e 'docker_registry_host="${REGISTRY_HOST}"'
		-e 'image_name="explorer"' \
		-e 'image_tag="${IMAGE_TAG}"' \
		-e 'unique_token="${UNIQUE_TOKEN}"' \
		-e 'version_id="${VERSION_ID}"'`


## Installing

### Install a released version using the Helm repository

* Add the repo where this chart lives:
`helm repo add local https://example.helm.server.url`

* Download the chart: `helm pull --untar runzero-explorer`

* Modify the **image.repository** and **image.tag** values in runzero-explorer/values.yaml.

* Install it: `helm install `

## Configuration

| field | description | default |
|-|-|-|
| `imagePullSecrets.enabled`| if true use the list of named imagePullSecrets | false |
| `imagePullSecrets.value`| a list if named secret references of the form `- name: secretName`| [] |
| `image.repository` | the repository of the image |  |
| `image.tag`| the tag of the image to use |  |
| `image.pullPolicy` | the image pull policy to use | IfNotPresent |
