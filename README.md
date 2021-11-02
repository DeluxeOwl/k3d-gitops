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


- [helm](https://helm.sh/) for package management (with argo)
- [argocd](https://argo-cd.readthedocs.io/en/stable/) for cd
- [hashicorp vault](https://www.vaultproject.io/) for secret management
- [prometheus](https://prometheus.io/) + [grafana](https://grafana.com/) for monitoring
- [ory suite](https://www.ory.sh/) for identity, authorization (or [OPA](https://www.openpolicyagent.org/)?)
- [harbor](https://goharbor.io/) for container registry
- [gitea](https://gitea.io/en-us/)/[gitlab](https://about.gitlab.com/) for git
- [concourse](https://concourse-ci.org/)/[drone](https://www.drone.io/) CI (or [argo workflows](https://argoproj.github.io/workflows/)?)
- [rook](https://rook.io/)/[longhorn](https://longhorn.io/) for distributed storage
- [istio](https://istio.io/) for service mesh
- [traefik](https://doc.traefik.io/traefik/providers/kubernetes-ingress/) as ingress controller  
* [Falco](https://falco.org/) - to monitor suspicious activity  
* [cert-manager](https://cert-manager.io/) - to manage certificates inside k8s  
* [Calico](https://docs.projectcalico.org/getting-started/kubernetes/) - for network policies  
* [Loki](https://grafana.com/oss/loki/) - for log aggregation  
* [Velero](https://velero.io/) - for cluster backups  
* [OpenFaaS](https://www.openfaas.com/) - serverless functions
* [Linkerd](https://linkerd.io/) instead of Istio?

Based on [my reddit post on /r/kubernetes](https://www.reddit.com/r/kubernetes/comments/qju6qg/building_a_complete_cluster_locally/?sort=top)

After this `"project"` is done, I'm planning to do a full production ready cluster on Azure with terraform and azure services to replace the stack above.

# Install steps

Get argocd up and running: https://argo-cd.readthedocs.io/en/stable/getting_started/
