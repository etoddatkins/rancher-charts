# rancher-charts
UC Santa Barbara Information Assurance and Security Rancher-ized helm charts

These charts have been augmented to be able to be deployed with [Rancher](https://ranchermanager.docs.rancher.com/) a Kubernetes management tool to deploy and run clusters anywhere and on any provider.

## Charts

* runzero-explorer: runZero [Explorers](https://www.runzero.com/docs/installing-an-explorer/) Customized for a specific [Organization](https://www.runzero.com/docs/organizations/) in [runZero](https://www.runzero.com/)
* awx: A web-based user interface, REST API, and task engine built on top of [Ansible](https://github.com/ansible/ansible). It is one of the upstream projects for [Red Hat Ansible Automation Platform](https://www.ansible.com/products/automation-platform).

## Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

  helm repo add ucsb-iac https://etoddatkins.github.io/helm-charts

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run `helm search repo
ucsb-iac` to see the charts.

To install the <chart-name> chart:

    helm install my-<chart-name> ucsb-iac/<chart-name>

To uninstall the chart:

    helm delete my-<chart-name>