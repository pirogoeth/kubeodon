# kubeodon

Kubernetes configurations for running a Mastodon instance.


## Notes

[Rook](https://rook.io) is used as the storage provisioner. If you're not using Rook for your cluster, make sure
to configure your PVC correctly and replace the `volume` stanzas in `deployment.yaml` and `job.yaml`
with your new configuration.

Make sure to update `configmap.yaml` and `secrets.yaml` to configure your Mastodon instance.

[cert-manager](https://github.com/jetstack/cert-manager) is used to obtain TLS certificates from Lets Encrypt.
You can easily deploy cert-manager using this [Helm chart](https://github.com/kubernetes/charts/tree/master/stable/cert-manager).

The Mastodon image used in the configurations can easily be swapped out -- it is built directly from upstream Mastodon.
As of this writing, the latest version published is v2.3.3 at `containers.dev.maio.me/sjohnson/containers/mastodon:v2.3.3`.
