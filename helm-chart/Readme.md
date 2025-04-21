# EcoStream Helm Chart

You can install EcoStream on a Kubernetes cluster using the Helm Chart from this repository.

If you want to use a namespace other than `ecostream`, please update the values.yaml.

- install EcoStream:

```
helm upgrade --install ecostream ./ --namespace ecostream --create-namespace
```

- upgrade the deployment (if you made any modifications to the Chart):

```
helm upgrade ecostream ./ --reuse-values
```

- uninstall EcoStream:

```
helm uninstall ecostream
```
