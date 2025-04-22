# EcoStream Helm Chart

You can install EcoStream on a Kubernetes cluster using the Helm Chart from this repository.

If you want to use a namespace other than `ecostream`, please update the values.yaml.

- create ecostream namespace:

```
k create namespace ecostream
```

- install EcoStream:

```
helm upgrade --install ecostream ./ --namespace ecostream --create-namespace
```

- check pods status, you will see ecostream-import-data pod in error, that's normal:

```
k get pods
NAME                                  READY   STATUS      RESTARTS   AGE
ecostream-configure-resources-v9qdn   0/1     Completed   0          31s
ecostream-database-5d8984656f-lqsjj   1/1     Running     0          31s
ecostream-import-data-24948           0/1     Error       0          5s
ecostream-import-data-7nhp5           0/1     Error       0          31s
ecostream-manager-748694bcd4-xptlr    1/1     Running     0          31s
ecostream-visualizer-9fc44cc6-w4tt9   1/1     Running     0          31s
```

- upgrade the deployment (if you made any modifications to the Chart):

```
helm upgrade ecostream ./ --reuse-values
```

- uninstall EcoStream:

```
helm uninstall ecostream
```
