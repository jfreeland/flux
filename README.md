# flux

this is just a playground for my home and test clusters.

TODO:

- migrate https://artifacthub.io/packages/helm/alekc/changedetection to k8s from
  existing host container
- https://github.com/rancher/system-upgrade-controller
- consider: https://artifacthub.io/packages/helm/harbor/harbor

## sealsecrets

TODO:

- why isn't sealing strings working?

```bash
kubectl -n mynamespace create secret generic ctic-f6d --from-literal=some_thing=1234 --from-literal=other_thing=OMG567 --dry-run=client -o yaml > ctic-mld.yaml
kubeseal --format=yaml --cert=pub-sealed-secrets.pem < secret.yaml > sealedsecret.yaml
```

```bash
      annotations:
        sealedsecrets.bitnami.com/cluster-wide: 'true'
```
