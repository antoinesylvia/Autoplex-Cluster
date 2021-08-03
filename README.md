# Think-Pi-Nano+ Cluster
Nothing to see here yet, will hold the current state (application layer) for my Kubernetes K3s cluster (replicated from my self-hosted) Gitlab. This GitOps repo will also cover Kubernetes support tools and other self-hosted applications I'm running (includes guides). I'll be using Github pages for an associated blog tied to this project: https://antoinesylvia.github.io/Think-Pi-Nano-Cluster/

Below is a list (v0.1) of support tools for my Think Pi Nano+ Cluster, these were discovered in:
- https://dockerlabs.collabnix.com/kubernetes/kubetools
- https://github.com/tomhuang12/awesome-k8s-resources
- https://www.cncf.io (Projects: Sandbox, Incubating, and Graduated)

# Grab Apps
- Helm Charts:
  - Artificate Hub (https://artifacthub.io/packages/search?kind=0&sort=relevance&page=1)
  - Arkade (https://github.com/alexellis/arkade)

# Backup and Storage
- Backup - Velero (https://github.com/vmware-tanzu/velero) and cloud storage (GCP, AWS, BackBlaze etc.)
- Storage - TrueNAS (https://www.truenas.com) and still looking at some others for block storage.

# Component Tools
- ConfigMap - Reloader (https://github.com/stakater/Reloader)
- Images - 
- Scheduler - Descheduler (https://github.com/kubernetes-sigs/descheduler)

# Games (Chaos) <---- Bartop arcade which is adjacant to the my homelab, serves as a client to run the games below.
- Kill pods through a videogame: 
  - KubeInvaders (https://github.com/lucky-sideburn/KubeInvaders) 
  - Kube-Chaos (https://github.com/Shogan/kube-chaos)
  - Kube Doom (https://github.com/storax/kubedoom)

# GitOps and Automation
- Config Management:
  - Ansible (https://github.com/ansible/ansible) 
  - AWX (https://github.com/ansible/awx)
- App Delivery Workflow - Devtron (https://github.com/devtron-labs/devtron)
- CI - Gitlab CI (https://docs.gitlab.com/ee/ci/)
- CD - ArgoCD (https://argoproj.github.io/argo-cd/)
- Docs as Code - Backstage (https://backstage.io/)
- Event Based Scrpting:
  - KEDA (https://github.com/kedacore/keda)
  - Argo Events (https://github.com/argoproj/argo-events)
- SSH (Multi) - Tmux (https://github.com/tmux/tmux)
- Package Management related:
  - Nova (https://github.com/fairwindsops/nova) Note: Will compare featureset against Renovate soon, specializes in dependencies.
  - Helm (https://github.com/helm/helm)
- Registry - Harbor (https://github.com/goharbor/harbor)
- Git Repo (Gitlab will replicate to Github):
  - Private (self hosted) - Gitlab (https://about.gitlab.com/)
  - Public - Github (https://github.com)
- IDE - Code-Server (VS Code) (https://github.com/cdr/code-server)
- Infrastructure Provisioner (For cloud K3s workers, doubtful I'll use Proxmox VMs locally) - Terraform (https://github.com/hashicorp/terraform)

# Kubernetes Distro and Base OS
- Distro - K3s (https://github.com/k3s-io/k3s)
  - Bootstrap: https://github.com/alexellis/k3sup
- OS level (Still evaluating Talos, API focus over SSH):
  - Ubuntu Server 20.04 for ARM, 64-bit (https://ubuntu.com/download/raspberry-pi)
  - Ubuntu Server 20.04 for x86/64 (https://ubuntu.com/download/server)

# Management, Monitoring and Observability 
- CLI (Management) - K9s (https://github.com/derailed/k9s)
- Dash - Lens (https://github.com/lensapp/lens)
- Mobile App - KubeNAV
- Alerts/Notifications - BotKube....TBD
- Pi Visibility - RPi-Monitor
- Testing - Powerseal (injects failure), Kube-burner(stress testing), Kubectl-debug (debug running pods)
- Monitoring - Pixie (x86/64, no ARM at the moment)
- Logging - Loki (Promtail agent)
- Health - KubeEye

# Networking
- DNS - CoreDNS (default)
- Ingress Controller - Nginx (Replacing Traefik)
- Load Balancer - Metallb
- VPN (Wireguard based) - Drago, Tailscale
- Local Resources - Mount or Ktunnel
- Container Network Interface - Flannel (default) but enabled IPsec or Wireguard (between nodes/pods, still researching this and features at the service mesh level)

# Optimization
- Clean-up Manifests - Kubectl-neat (https://github.com/itaysk/kubectl-neat)

# Runtime
- Runtime - ContainerD (default)

# Security
- Certs - Cert Manager (https://github.com/jetstack/cert-manager)
- Misconfigs - TBD as this will be used with Gitlab CI, evaluating Popeye, Kube-Bench, Kube Linter
- Vulnerabilities - Deepfence Runtime ThreatMapper (used for containers, images, hosts and registries/repositories), Kube-Hunter
- Policy - Kyverno (https://github.com/kyverno/kyverno)
- Object Definitions - Kube-Score (https://github.com/zegl/kube-score)
- RBAC:
  - Permission-Manager (https://github.com/sighupio/permission-manager)
  - Kubectl who-can (https://github.com/aquasecurity/kubectl-who-can)
  - Teleport (https://github.com/gravitational/teleport)
- Secrets (TBD after digging through articles and many Reddit threads): 
  - 1A = Hashicorp Vault (https://github.com/hashicorp/vault) w/Kubernetes external secrets plugin (https://github.com/external-secrets/kubernetes-external-secrets)
  - 1B = Sealed-Secrets (https://github.com/bitnami-labs/sealed-secrets)
- Service Mesh - LinkerD (https://github.com/linkerd/linkerd2)

# Serverless 
- Serverless - OpenFaaS (https://github.com/openfaas/faas)

# zOther
- Google Coral
- Intel Compute Stick
- Nvidia Jetson Nano
- Blinkt Lights
