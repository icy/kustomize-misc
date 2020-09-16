## Description

If a patch specifies (any) `namespace` as part of its target,
the patch will select all deployments that has `default` as namespace.

### Actual output

```
$ kustomize version
{Version:kustomize/v3.8.2 GitCommit:e2973f6ecc9be6187cfd5ecf5e180f842249b3c6 BuildDate:2020-08-29T17:44:01Z GoOs:linux GoArch:amd64}

$ kustomize build |grep mine/group
        mine/group: my_worker_group
        mine/group: default
```

### Expected output

```
$ kustomize build |grep mine/group
        mine/group: my_worker_group
        mine/group: my_worker_group
```
