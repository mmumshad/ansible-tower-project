# Ansible Role: azure-aks

## Create namespace on kubernetes cluster and deploy test application

Pre-Requisite:

Requires Kubernetes cluster to be created and kubeconfig file to be present.

Require

`pip install openshift`


## variables

```
kubeconfig_file_path: tests/aks-kubeconfig.yaml
kubeconfig_context: test-aks-kubeconfig
kube_app_state: absent
kube_namespace: testing
```
