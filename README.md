# k3d-gitops

This is a repo of my yaml files for kubernetes (k3d for local dev) + gitops using ArgoCD **for learning purposes**.

# Tools

- I'm using [k3d](https://k3d.io) for development and learning.

  ```sh
  $ k3d cluster create -p "80:80@loadbalancer" --agents 2
  ```

- For **subdomains** on my local machine, I'm using https://sslip.io/ as a DNS service (this works since k3d uses traefik behind the scenes as an ingress controller).

  In short, something like `nginx.127-0-0-1.sslip.io` resolves to `127.0.0.1` (see [main-ing.yaml](./main-ing.yaml) for more examples).

# Planned installs:

Going for the full open source stack.

- helm for package management
- argocd for cd on kubernetes
- hashicorp vault for secret management
- prometheus + grafana for monitoring
- ory suite for identity, authorization (or OPA?) 
- harbor for registry
- gitea/gitlab for git + concourse/drone CI + dev pipeline (or argoworkflows?)
- rook/ceph/longhorn for storage (hard with k3d?)
- istio for service mesh
- traefik as ingress controller

After this `"project"` is done, I'm planning to do a full production ready cluster on Azure with terraform and azure services to replace the stack above.

# Install steps

Get argocd up and running: https://argo-cd.readthedocs.io/en/stable/getting_started/
