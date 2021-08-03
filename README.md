# Think-Pi-Nano+ Cluster
Nothing to see here yet, will hold the current state (application layer) for my Kubernetes cluster (replicated from my self-hosted) Gitlab. This GitOps repo will also cover Kubernetes support tools and other self-hosted applications I'm running (includes guides). 

Think Pi Nano+ Cluster support tools v0.1 (some are still under review):
# Management, Monitoring and Observability 
- CLI (Management) - K9s
- Dash - Lens
- Mobile App - KubeNAV
- Alerts/Notifications - BotKube....TBD
- Pi Visibility - RPi-Monitor
- Testing - Powerseal (injects failure), Kube-burner(stress testing), Kubectl-debug (debug running pods)
- Monitoring - Pixie(x86/64)
- Logging - Loki (Promtail agent)
- Health - KubeEye

# Networking
- DNS - CoreDNS
- Ingress Controller - Nginx
- Load Balancer - Metallb
- VPN (Wireguard based) - Drago, Tailscale
- Local Resources - Mount or Ktunnel
- Container Network Interface - Flannel (default) but enabled IPsec or Wireguard (between nodes/pods, still researching this and features at the service mesh level)

# Optimization
- Clean-up Manifests - Kubectl-neat

# Package Management, Registry (artifacts) and GIT repo
- Package Management related - Nova (checks helm charts for updates will compare featureset against Renovate soon, specializes in dependencies), Helm (charts, yml)
- Registry - Harbor (scan images, sign, take action and more)
- Repo - Private (self hosted) - Gitlab (will replicate to Github or vice-versa)
- Repo - Public - Github

# Runtime
- Runtime - ContainerD
