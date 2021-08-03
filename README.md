# Think-Pi-Nano+ Cluster
Nothing to see here yet, will hold the current state (application layer) for my Kubernetes cluster (replicated from my self-hosted) Gitlab. This GitOps repo will also cover Kubernetes support tools and other self-hosted applications I'm running (includes guides). 

Think Pi Nano+ Cluster support tools v0.1 (some are still under review) featured below, I've discovered in:
- https://dockerlabs.collabnix.com/kubernetes/kubetools/
- https://github.com/tomhuang12/awesome-k8s-resources
- https://www.cncf.io/ (Projects: Sandbox, Incubating, and Graduated)

# Apps
- Helm Charts - Artificate Hub (UI) and Arkade (CLI)

# Backup and Storage
- Backup - Velero and connect to cloud account.
- Storage - TrueNAS and still looking at some others for block storage.

# Component Tools
- ConfigMap - Reloader 
- Images - 
- Scheduler - Descheduler

# Games (Chaos)
- Kill pods through a videogame - KubeInvaders, Kube-Chaos, and Kube Doom

# GitOps and Automation
- Config Management - Ansible (https://github.com/ansible/ansible) - AWX (https://github.com/ansible/awx)
- App Delivery Workflow - Devtron
- CI - Gitlab CI
- CD - ArgoCD
- Docs as Code - Backstage
- Event Based Scrpting - KEDA, Argo Events
- SSH (Multi) - Tmux
- Package Management related - Nova (checks helm charts for updates will compare featureset against Renovate soon, specializes in dependencies), Helm (charts, yml)
- Registry - Harbor (scan images, sign, take action and more)
- Git Repo - Private (self hosted) - Gitlab (will replicate to Github or vice-versa)
- Git Repo - Public - Github
- IDE - Code-Server (Vs)
- Infrastructure Provisioner - Terraform (for cloud workers, doubtful I'll use Proxmox VMs locally)

# Kubernetes Distro
- Distro - K3s (over MicroK8s and K8s)
- OS level - Ubuntu 20.04, evalating Talos (API focus over SSH)


# Management, Monitoring and Observability 
- CLI (Management) - K9s
- Dash - Lens
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
- Clean-up Manifests - Kubectl-neat

# Runtime
- Runtime - ContainerD (default)

# Security
- Certs - Cert Manager 
- Misconfigs - TBD as this will be used with Gitlab CI, evaluating Popeye, Kube-Bench, Kube Linter
- Vulnerabilities - Deepfence Runtime ThreatMapper (used for containers, images, hosts and registries/repositories), Kube-Hunter
- Policy - Kyverno
- Object Definitions - Kube-Score
- RBAC - Permission-Manager, Kubectl who-can, Teleport
- Secrets - TBD after digging through articles and many Reddit threads: 1A = Hashicorp Vault w/Kubernetes external secrets plugin and 1B = Sealed-Secrets 
- Service Mesh - LinkerD

# Serverless 
- Serverless - OpenFaaS

# zOther
- Google Coral
- Intel Compute Stick
- Nvidia Jetson Nano
- Blinkt Lights
