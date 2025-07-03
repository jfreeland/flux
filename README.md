# flux

my homelab playground.

TODO:

- persistent volumes
- IAM anywhere
- ceph
- thanos
- https://artifacthub.io/packages/helm/alekc/changedetection
- https://github.com/rancher/system-upgrade-controller
- https://artifacthub.io/packages/helm/harbor/harbor
- Tailscale?

## sealedsecrets

```bash
kubectl -n mynamespace create secret generic mysecret --from-literal=some_thing=123 --from-literal=other_thing=OMG456 --dry-run=client -o yaml > tempsecret.yaml
kubeseal --scope=cluster-wide --format=yaml --cert=pub-sealed-secrets.pem < tempsecret.yaml > sealedsecret.yaml
```
