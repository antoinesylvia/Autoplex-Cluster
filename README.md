# Think-Pi-Nano+ | Cluster Support Tools
Nothing to see here yet, will hold the current state (application layer) for my Kubernetes K3s cluster (replicated from my self-hosted) Gitlab. This GitOps repo will also cover Kubernetes support tools and other self-hosted applications I'm running (includes guides). I'll be using Github pages for an associated blog tied to this project: https://antoinesylvia.github.io/Think-Pi-Nano-Cluster/

Below is a list (v0.1) of support tools for my Think Pi Nano+ Cluster, will consolidate some more as I go. These tools were discovered in:
- https://dockerlabs.collabnix.com/kubernetes/kubetools
- https://github.com/tomhuang12/awesome-k8s-resources
- https://www.cncf.io (Projects: Sandbox, Incubating, and Graduated)
- https://www.reddit.com/r/kubernetes

# Backup and Storage
- Backup - Velero (https://github.com/vmware-tanzu/velero) and cloud storage (GCP, AWS, BackBlaze etc.)
- Storage - TrueNAS (https://www.truenas.com) and still looking at some others for block storage.

# Component Support Tools
- ConfigMap - Reloader (https://github.com/stakater/Reloader)
- Scheduler - Descheduler (https://github.com/kubernetes-sigs/descheduler)

# Games (Chaos) | Arcade adjacant to my homelab will run the games below (serves as a client) 
- Kill pods through a videogame: 
  - Kube-Chaos (https://github.com/Shogan/kube-chaos)
  - Kube Doom (https://github.com/storax/kubedoom
  - KubeInvaders (https://github.com/lucky-sideburn/KubeInvaders) 

# GitOps and Automation
- Config Management:
  - Ansible (https://github.com/ansible/ansible) 
    - AWX (https://github.com/ansible/awx)
- App Delivery Workflow - Devtron (https://github.com/devtron-labs/devtron)
- App Package Management:
  - Helm (https://github.com/helm/helm)
    - Arkade (https://github.com/alexellis/arkade)
    - Artificate Hub (https://artifacthub.io/packages/search?kind=0&sort=relevance&page=1)
      - K8s@home (https://artifacthub.io/packages/search?page=1&org=k8s-at-home)
    - Ahoy - Helm GUI (https://github.com/oslabs-beta/Ahoy) 
    - Renovate - Helm | Dependency Updater (https://github.com/renovatebot/renovate) 
- CI - Gitlab CI (https://docs.gitlab.com/ee/ci/)
- CD - ArgoCD (https://argoproj.github.io/argo-cd/)
- Docs as Code - Backstage (https://backstage.io/)
- Event Based Scripting:
  - KEDA (https://github.com/kedacore/keda)
  - Argo Events (https://github.com/argoproj/argo-events)
- Git Repo (Gitlab will replicate to Github):
  - Private (self hosted) - Gitlab (https://about.gitlab.com/)
  - Public - Github (https://github.com)
- IDE - Code-Server (VS Code) (https://github.com/cdr/code-server)
- Image Docker - Dive (Explore layers of Docker image) (https://github.com/wagoodman/dive)
- Image Registry 
  - Private - Harbor (https://github.com/goharbor/harbor)
  - Public 
    - Dockerhub (https://hub.docker.com/)
      - Linuxserver (https://fleet.linuxserver.io/)
      - Hotio (https://hotio.dev/)
    - Github (https://ghcr.io) 
- Infrastructure Provisioner (For cloud K3s workers or locally using Proxmox VMs) - Terraform (https://github.com/hashicorp/terraform)
- SSH (Multi) - Tmux (https://github.com/tmux/tmux)

# Images (OS)
  - Burn/generate many Linux OS images to SD cards for cluster:
    - Cloudmesh-pi-burn (https://github.com/cloudmesh/cloudmesh-pi-burn)
    - Clusperry installer (https://github.com/nullxx/clusperry-installer)
  - Build machine images for multiple platforms:
    - Proxmox Packer builder (https://www.packer.io/docs/builders/proxmox)
      - Packer (https://github.com/hashicorp/packer)

# Kubernetes Distro and Base OS
- Distro - K3s (https://github.com/k3s-io/k3s)
  - Bootstrap: https://github.com/alexellis/k3sup
- OS level (Still evaluating Talos, API focus over SSH):
  - Ubuntu Server 20.04 for ARM (used for Raspberry Pis), 64-bit (https://ubuntu.com/download/raspberry-pi)
  - Ubuntu Server 20.04 for x86/64 (used for Thinkpad laptops) (https://ubuntu.com/download/server)
  - Linux4Tegra (used for Jetson Nanos) (https://developer.nvidia.com/embedded/linux-tegra-archive)

# Management, Monitoring and Observability 
- CLI (Management) - K9s (https://github.com/derailed/k9s)
- Dash:
  - Lens (https://github.com/lensapp/lens)
    - Extension - Lens Resource Map (https://github.com/nevalla/lens-resource-map-extension)
    - Extension - Starboard (https://github.com/aquasecurity/starboard)
- Health - KubeEye (https://github.com/kubesphere/kubeeye)
- Logging:
  - Loki (Promtail agent) (https://github.com/grafana/loki)
    - Syslog-ng (run a host level, send logs to Loki) (https://github.com/syslog-ng/syslog-ng)   
- Mobile App - KubeNAV (https://github.com/kubenav/kubenav)
- Monitoring: 
  - Pixie (x86/64, no ARM at the moment) (https://github.com/pixie-labs/pixie)
  - Grafana (can use Pixie as datasource) (https://github.com/grafana/grafana)
     - Prometheus (https://github.com/prometheus/prometheus)
     - Alerts/Notifications: Native channels in Grafana (Teams, Slack etc.) | Backup: BotKube
- Pi Visibility - RPi-Monitor (https://github.com/XavierBerger/RPi-Monitor)
- Testing:
  - Powerfulseal (injects failure) (https://github.com/powerfulseal/powerfulseal)
  - Kube-burner(stress testing) (https://github.com/cloud-bulldozer/kube-burner)
  - Kubectl-debug (debug running pods) (https://github.com/cloud-bulldozer/kube-burnerKubectl-debug)

# Networking
- Container Network Interface - Flannel (default) but enabled IPsec or Wireguard (between nodes/pods, still researching this and features at the service mesh level)
- DNS - CoreDNS (default)
- Ingress Controller - Nginx (Replacing Traefik) (https://github.com/kubernetes/ingress-nginx)
- Load Balancer - Metallb (https://github.com/metallb/metallb)
- Local Resources - Mount or Ktunnel (https://github.com/omrikiei/ktunnel?utm_sq=g93l33gmsu)
- VPN (Wireguard based, testing the following):
  - Drago (https://github.com/seashell/drago)
  - Netmaker (https://github.com/gravitl/netmaker)
  - Tailscale (https://github.com/tailscale/tailscale)
  
# Optimization
- Clean-up Manifests - Kubectl-neat (https://github.com/itaysk/kubectl-neat)

# Runtime
- Runtime - ContainerD (default)

# Security
- Certs - Cert Manager (https://github.com/jetstack/cert-manager)
- Misconfigs - TBD as this will be used with Gitlab CI, evaluating Popeye, Kube-Bench, Kube Linter
- Vulnerabilities:
  - Deepfence Runtime ThreatMapper (https://github.com/deepfence/ThreatMapper) Note: Used for containers, images, hosts and registries/repositories.
  - Kube-Hunter (Pen Test) (https://github.com/aquasecurity/kube-hunter)
- Policy - Kyverno (https://github.com/kyverno/kyverno)
- Object Definitions - Kube-Score (https://github.com/zegl/kube-score)
- RBAC:
  - Permission-Manager (https://github.com/sighupio/permission-manager)
  - Kubectl who-can (https://github.com/aquasecurity/kubectl-who-can)
  - Teleport (https://github.com/gravitational/teleport)
- Secrets (TBD after digging through articles and many Reddit threads): 
  - 1A. Hashicorp Vault (https://github.com/hashicorp/vault) w/Kubernetes external secrets plugin (https://github.com/external-secrets/kubernetes-external-secrets)
  - 1B. Sealed-Secrets (https://github.com/bitnami-labs/sealed-secrets)
  - 1C. Mozilla SOPS (https://github.com/mozilla/sops)
- Service Mesh - LinkerD (https://github.com/linkerd/linkerd2)

# Serverless 
- Serverless - OpenFaaS (https://github.com/openfaas/faas)

# Tools - Hardware
- Google Coral (https://coral.ai/docs/accelerator/get-started/#next-steps)
- Intel Compute Stick (https://software.intel.com/content/www/us/en/develop/articles/get-started-with-neural-compute-stick.html)
- Nvidia Jetson Nano (https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit)
- Raspberry Pi (https://projects.raspberrypi.org/en/projects/raspberry-pi-getting-started/)
- Blinkt Lights for Pi/Nano (https://learn.pimoroni.com/tutorial/sandyj/getting-started-with-blinkt)

# zOther - People I follow to learn more about Docker and/or Kubernetes
- Ajeet Singh Raina (https://twitter.com/ajeetsraina)
- Alex Ellis (https://twitter.com/alexellisuk)
- Ian Coldwater (https://twitter.com/IanColdwater)
- Jeff Geerling (https://twitter.com/geerlingguy)
- Jessie Frazelle (https://twitter.com/jessfraz)
- Julia Evans (https://twitter.com/b0rk)
- Kelsey Hightower (https://twitter.com/kelseyhightower)
- Nana Tech World (https://www.youtube.com/channel/UCdngmbVKX1Tgre699-XLlUA)

