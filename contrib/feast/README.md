# Feast Kustomize

## Installing with Kustomize

### Add Helm Repo
Add the helm repo to the local. You can find more information about the helm chart [here](https://github.com/feast-dev/feast/blob/master/infra/charts/feast-feature-server/README.md)

```shell
helm repo add feast-charts https://feast-helm-charts.storage.googleapis.com
helm repo update
```

### Standalone

Execute below commands to install registry server
```
make feast/registry-server
kustomize build feast/base | kubectl apply -n feast -f -
```

Execute below commands to install online server
```
make feast/online-server
kustomize build feast/base | kubectl apply -n feast -f -
```

Execute below commands to install offline server
```
make feast/offline-server
kustomize build feast/base | kubectl apply -n feast -f -
```

Execute below commands to install UI server
```
make feast/ui-server
kustomize build feast/base | kubectl apply -n feast -f -
```

### With Kubeflow
TBD
