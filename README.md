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
kubectl -n mynamespace create secret generic mysecret --from-literal=some_thing=123 --from-literal=other_thing=OMG456 --dry-run=client -o yaml > tempsecret.yaml
kubeseal --scope=cluster-wide --format=yaml --cert=pub-sealed-secrets.pem < tempsecret.yaml > sealedsecret.yaml
```

```bash
      annotations:
        sealedsecrets.bitnami.com/cluster-wide: 'true'
```
