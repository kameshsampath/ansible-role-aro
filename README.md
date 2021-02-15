# Ansible role for Azure Red Hat OpenShift(ARO)

__NOTE__: WORK IN PROGRESS 

Ansible to create/update/delete Azure Red Hat OpenShift clusters.

## Requirements

- [Docker Desktop](https://www.docker.com/products/docker-desktop) or Docker for Linux

- [Ansible](https://ansible.com) >= v2.9.10

## Prepare Environment

```shell
pip3 install \
  -r https://raw.githubusercontent.com/kameshsampath/ansible-role-openshift-spices/master/requirements.txt
pip3 -r install -r https://raw.githubusercontent.com/ansible-collections/azure/dev/requirements-azure.txt
ansible-galaxy role install kameshsampath.aro
ansible-galaxy collection install community.kubernetes
ansible-galaxy collection install azure.azcollection
```

__NOTE__: For Windows its recommended to use Windows Subsystem for Linux (WSL)

## Role Dependencies

- kameshsampath.openshift_app_spices

## Role Variables

| Variable Name| Description | Default |
|--|--|--|
| kubernetes_cluster_type | The Kubernetes Cluster Type minikube or kind or custom | minikube |
| k8s_cluster_ip | The Kubernetes Cluster IP | Auto configured for minikube or KinD |
| deploy_knative | Deploy Knative | False |
| knative_version | The Knative version | v0.16.0 |
| knative_serving_version | The Knative Serving version | v0.16.0 |
| knative_eventing_version | The Knative Eventing version | v0.16.0 |
| deploy_ingress | Deploy Ingress | True |
| ingress_namespace | The namespace for Contour Ingress | contour-system |
| ingress_namespace | The namespace for Contour Ingress | contour-system |
| ingress_manifest  | The Contour Ingress manifest file  | [Project Contour](https://projectcontour.io/quickstart/contour.yaml) |
| deploy_tektoncd | Deploy Tektoncd | False |
| tektoncd_pipelines_version | Tektoncd Pipelines Version | v0.11.3 |
| tektoncd_triggers_version | Tektoncd Triggers Version | v0.4.0 |
| deploy_argocd | Deploy [Argo CD](https://argoproj.github.io/) | False |
| argocd_namespace | Argo CD namespace | argocd |
| argocd_version | Argo CD version to use | v1.6.2 |
| deploy_skupper | Deploy [](skupperhttps://skupper.io) | False |
| skupper_namespace | Namespace to deploy skupper | default |
| skupper_cli_download | Download Skupper CLI | True |
| skupper_site_name | Name of the Skupper site to create | mysite |
| skupper_site_edge | Is this a skupper edge site | False |
| skupper_console_enable | Enable Skupper Console | true |
| skupper_router_console_enable | Enable Skupper router Console | true |
| skuper_cluster_local | Is Skupper local to cluster | false |
| skupper_console_authentication | Skupper Console Authentication | unsecured |
| skupper_console_password | Skupper Console User password | skupp3r! |
| skupper_console_user | Skupper Console User | skupper |

## Example Playbooks

The [examples](https://github.com/kameshsampath/ansible-role-aro/master/examples) directory has various playbook examples to get started using this role

## License

[Apache v2](https://github.com/kameshsampath/ansible-role-aro/tree/master/LICENSE)

## Author Information

[Kamesh Sampath](mailto:kamesh.sampath@hotmail.com)

## Issues

[Issues](https://github.com/kameshsampath/ansible-role-aro/issues)
