👋 Nothing to see here yet, will hold the current state (application layer) for my Kubernetes K3s cluster (replicated from my self-hosted) Gitlab. This GitOps repo will also cover Kubernetes support tools and other self-hosted applications I'm running (includes guides). Cluster is comprised of Raspberry Pis (3 & 4), Jetson Nanos and a bunch of old Thinkpads I've collected over the years. I physically assembled the cluster when I had a tiny bit of free time during paternity leave in the summer of 2021. Now with 2 little ones, I try to work on this (software and automation side) late at night when everyone is asleep. I was originally inspired to go big on this (before crazy price increases for Pi and Nano) by a local member project at Dallas Makerspace that had his project posted around the web: 
 - https://hackaday.com/2014/02/17/40-node-raspi-cluster/
 - https://dallasmakerspace.org/wiki/40-node_Raspberry_Pi_Cluster

I'll be using Github pages for an associated blog tied to this project: https://antoinesylvia.github.io/Autoplex-Cluster/

Note: Other people that will have access to this cluster will be my cousins looking to attain hands-on skills needed for their pursuit of entry level jobs, wife (engineer) and friends (security engineers) when it's all said and done. One step at a time.

![1](https://github.com/antoinesylvia/Autoplex-Cluster/blob/main/Kubernetes_After_Dark.jpg)

Hardware information and cluster pictures can be found here: https://github.com/antoinesylvia/Autoplex-Cluster/tree/main/hardware_info


Image 1 (Pi 4s & old HP Microserver (persistant storage)       |  Image 2 (Pi 4s & Pi 3s)
:-------------------------:|:-------------------------:
![](https://github.com/antoinesylvia/Think-Pi-Nano-Cluster/blob/main/hardware_info/1a.jpg)  |  ![](https://github.com/antoinesylvia/Think-Pi-Nano-Cluster/blob/main/hardware_info/2a.jpg)

Image 3 (Jetson Nanos)        |  Image 4 (Old Thinkpads and my custom built desktops)
:-------------------------:|:-------------------------:
![](https://github.com/antoinesylvia/Think-Pi-Nano-Cluster/blob/main/hardware_info/3a.jpg)  |  ![](https://github.com/antoinesylvia/Think-Pi-Nano-Cluster/blob/main/hardware_info/4a.jpg)

Image 5 (Gateway for LAN1/LAN2, Switch and old Pis)        |  Image 6 (Mgmt. Location)
:-------------------------:|:-------------------------:
![](https://github.com/antoinesylvia/Think-Pi-Nano-Cluster/blob/main/hardware_info/5a.jpg)  |  ![](https://github.com/antoinesylvia/Think-Pi-Nano-Cluster/blob/main/hardware_info/6a.jpg)

General Application information can be found here: https://github.com/antoinesylvia/Autoplex-Cluster/tree/main/general_apps_info

# Autoplex Cluster - Support Tools
--------------------------------------------------------------
Below is a list (v0.1) of support tools for my Think Pi Nano+ Cluster, will consolidate some more as I go. These tools were discovered in:
- https://dockerlabs.collabnix.com/kubernetes/kubetools
- https://github.com/tomhuang12/awesome-k8s-resources
- https://www.cncf.io (Projects: Sandbox, Incubating, and Graduated)
- https://www.reddit.com/r/kubernetes

# Backup and Storage
- Backup - Velero (https://github.com/vmware-tanzu/velero) and cloud storage (GCP, AWS, BackBlaze etc.)
- Storage - TrueNAS Core (https://www.truenas.com) 

# Component Support Tools
- ConfigMap - Reloader (https://github.com/stakater/Reloader)
- Scheduler - Descheduler (https://github.com/kubernetes-sigs/descheduler)

# GitOps and Automation
- Config Management:
  - Ansible (https://github.com/ansible/ansible) 
    - AWX - Ansible Web UI & Rest API (https://github.com/ansible/awx)
- App Delivery Workflow - Devtron (https://github.com/devtron-labs/devtron)
- App Package Management:
  - Helm (https://github.com/helm/helm)
    - ~~Arkade (https://github.com/alexellis/arkade)~~
    - Artificate Hub (https://artifacthub.io/packages/search?kind=0&sort=relevance&page=1)
      - K8s@home (https://artifacthub.io/packages/search?page=1&org=k8s-at-home)
    - ~~Ahoy - Helm GUI (https://github.com/oslabs-beta/Ahoy)~~
    - Renovate - Helm | Dependency Updater (https://github.com/renovatebot/renovate) 
- CI - ~~Gitlab CI (https://docs.gitlab.com/ee/ci/)~~ Github Actions (https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions)
- CD - ArgoCD (Includes RBAC for Git) (https://argoproj.github.io/argo-cd/)
- Docs as Code - Backstage (https://backstage.io/)
- Event Based Scripting:
  - KEDA (https://github.com/kedacore/keda)
  - ~~Events (https://github.com/argoproj/argo-events)~~
- Git Repo (Gitlab will replicate to Github):
  - Private (self hosted) - Gitlab (https://about.gitlab.com/)
  - Public - Github (https://github.com)
- IDE - Code-Server (VS Code) (https://github.com/cdr/code-server)
- Image Docker - Dive (Explore layers of Docker image) (https://github.com/wagoodman/dive)
- Image Registry 
  - Private - Harbor (Includes RBAC for registry)(https://github.com/goharbor/harbor)
  - Public 
    - Dockerhub (https://hub.docker.com/)
      - Linuxserver (https://fleet.linuxserver.io/)
      - Hotio (https://hotio.dev/)
    - Github (https://ghcr.io) 
- Infrastructure Provisioner (For cloud K3s workers or locally using Proxmox VMs) - Terraform (https://github.com/hashicorp/terraform)
- SSH (Multi) - Tmux (https://github.com/tmux/tmux)

# Images (OS)
  - Burn/generate many Linux OS images to SD cards for cluster:
    - ~~Cloudmesh-pi-burn (https://github.com/cloudmesh/cloudmesh-pi-burn)~~
    - Clusperry installer (https://github.com/nullxx/clusperry-installer)
    - Raspbian image builder (https://github.com/RPi-Distro/pi-gen)
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
  - Lens $$ (includes RBAC tied to cluster) (https://github.com/lensapp/lens), OpenLens (https://github.com/MuhammedKalkan/OpenLens/releases) or Octant (https://octant.dev/)
    - Extension - Lens Resource Map (https://github.com/nevalla/lens-resource-map-extension)
    - ~~Extension - Starboard (https://github.com/aquasecurity/starboard)~~
- Health 
  - KubeEye (https://github.com/kubesphere/kubeeye)
  - Popeye (https://github.com/derailed/popeye)
- Logging:
  - Stern (Log tailing) (https://github.com/stern/stern)
  - Loki (Promtail agent) (https://github.com/grafana/loki)
    - Syslog-ng (run at host level, send logs to Loki) (https://github.com/syslog-ng/syslog-ng)   
- Mobile App - KubeNAV (https://github.com/kubenav/kubenav)
- Monitoring: 
  - Pixie (x86/64, no ARM at the moment) (https://github.com/pixie-labs/pixie)
  - Grafana (can use Pixie as datasource) (https://github.com/grafana/grafana)
     - Prometheus (https://github.com/prometheus/prometheus)
  - BotKube (Alerts/Notifications for Discord/Slack) (https://github.com/kubeshop/botkube) 
  - Uptime-Kuma (Uptime Robot replacement, host offsite in cloud w/ Wireguard link) (https://github.com/louislam/uptime-kuma)
- ~~Pi Visibility - RPi-Monitor (https://github.com/XavierBerger/RPi-Monitor)~~
- Testing (pick 1):
  - Powerfulseal (injects failure) (https://github.com/powerfulseal/powerfulseal)
  - Kube-burner(stress testing) (https://github.com/cloud-bulldozer/kube-burner)
  - ~~Kubectl-debug (debug running pods) (https://github.com/cloud-bulldozer/kube-burnerKubectl-debug)~~
  - Kube-Chaos (kill pods via game) (https://github.com/Shogan/kube-chaos)
  - Kube Doom (kill pods via game) (https://github.com/storax/kubedoom
  - KubeInvaders (kill pods via game) (https://github.com/lucky-sideburn/KubeInvaders) 

# Networking
- Container Network Interface - Flannel (default) but enabled IPsec or Wireguard (between nodes/pods, still researching this and features at the service mesh level)
- DNS - CoreDNS (default)
- Ingress Controller - Ingress-Nginx (Replacing Traefik) (https://github.com/kubernetes/ingress-nginx)
  - SSO/2FA/Auth - Authelia (https://github.com/authelia/authelia)
- Load Balancer - Metallb (https://github.com/metallb/metallb)
- ~~Local Resources - Mount or Ktunnel (https://github.com/omrikiei/ktunnel?utm_sq=g93l33gmsu)~~
- VPN (Wireguard based, testing the following to help extend the cluster offsite):
  - ~~Drago (https://github.com/seashell/drago)~~
  - Netmaker (self-host only, kernel wireguard, least polished) (https://github.com/gravitl/netmaker)
  - Tailscale (https://github.com/tailscale/tailscale)
  
# Optimization
- Clean-up Manifests - Kubectl-neat (https://github.com/itaysk/kubectl-neat)

# Runtime
- Runtime - ContainerD (https://github.com/containerd/containerd)

# Security
- Certs - Cert Manager (https://github.com/jetstack/cert-manager)
- Misconfigs
  - Kube-Bench (CIS check) (https://github.com/aquasecurity/kube-bench)
  - Kube Linter (Checks YAML or Helm Charts) (https://github.com/stackrox/kube-linter)
- Vulnerabilities:
  - Deepfence Runtime ThreatMapper (https://github.com/deepfence/ThreatMapper) Note: Used for containers, images, hosts and registries/repositories (supports Harbor).
  - Kube-Hunter (Pen Test) (https://github.com/aquasecurity/kube-hunter)
- Policy - Kyverno (https://github.com/kyverno/kyverno)
- Object Definitions - Kube-Score (https://github.com/zegl/kube-score)
- RBAC:
  - Permission-Manager (https://github.com/sighupio/permission-manager)
  - ~~Kubectl who-can (https://github.com/aquasecurity/kubectl-who-can)~~
  - Teleport (Identity Native Proxy) (https://github.com/gravitational/teleport)
- Secrets (TBD after digging through articles and many Reddit threads): 
  - 1A. Hashicorp Vault (https://github.com/hashicorp/vault) ~~w/Kubernetes external secrets plugin (https://github.com/external-secrets/kubernetes-external-secrets)~~
  - 1B. Sealed-Secrets (https://github.com/bitnami-labs/sealed-secrets)
  - 1C. Mozilla SOPS (https://github.com/mozilla/sops)
- Service Mesh - LinkerD (https://github.com/linkerd/linkerd2)
  - Someone made a document comparing all the service mesh options, please note not all support ARM: https://docs.google.com/spreadsheets/d/1Bxf8VW9n-YyHeBiKdXt6zytOgw2cQlsDnK1gLUvsZ4A/edit#gid=907731238  

# Serverless 
- Serverless - OpenFaaS (https://github.com/openfaas/faas)

# Tools - Hardware
- Google Coral (https://coral.ai/docs/accelerator/get-started/#next-steps)
- Intel Compute Stick (https://software.intel.com/content/www/us/en/develop/articles/get-started-with-neural-compute-stick.html)
- Nvidia Jetson Nano (https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit)
- Raspberry Pi (https://projects.raspberrypi.org/en/projects/raspberry-pi-getting-started/)
- Blinkt Lights for Pi/Nano (https://learn.pimoroni.com/tutorial/sandyj/getting-started-with-blinkt)

# zOther - People I follow to learn more about Docker, Kubernetes, DevOps, and/or ARM
- Ajeet Singh Raina (https://twitter.com/ajeetsraina)
- Alex Ellis (https://twitter.com/alexellisuk) (author of https://github.com/alexellis/k3sup)
- Anais Urlichs (https://www.youtube.com/c/AnaisUrlichs)
- DevOps Toolkit (https://www.youtube.com/channel/UCfz8x0lVzJpb_dgWm9kPVrw)
- Ian Coldwater (https://twitter.com/IanColdwater)
- Jeff Geerling (https://twitter.com/geerlingguy)
- Jessie Frazelle (https://twitter.com/jessfraz)
- Julia Evans  (https://twitter.com/b0rk)
- Kelsey Hightower (https://twitter.com/kelseyhightower)
- Maria Markstedter (https://twitter.com/fox0x01)
- Nana Tech World (https://www.youtube.com/channel/UCdngmbVKX1Tgre699-XLlUA)
- Network Chuck (https://www.youtube.com/watch?v=X9fSMGkjtug)
- Techno Tim (https://www.youtube.com/c/TechnoTimLive)
- Daniele Polencic (https://twitter.com/danielepolencic) (author of the ultimate troubleshooting guide: https://twitter.com/manekinekko/status/1434808198532370432/photo/1)

# zUnderReview
- Carvel-YTT - YAML Templating Tool (https://github.com/vmware-tanzu/carvel-ytt) -promote
- ~~GlusterFS - Distributed File System (https://github.com/gluster/glusterfs)~~
- ~~Kruise - Application Mgmt. Automation (https://github.com/openkruise/kruise)~~
- KubeCTX - Faster way to switch between clusters and namespaces in KubeCTL (https://github.com/ahmetb/kubectx) -promote
- Kubernetes Goat - Vulnerable cluster by default (https://github.com/madhuakula/kubernetes-goat) -promote
- KubeShark - API Traffic Viewer ([https://github.com/up9inc/mizu](https://github.com/kubeshark/kubeshark)) -promote
- Nova - Find Deprecated Helm charts in cluster (https://github.com/FairwindsOps/nova) -promote
- ~~OSM - Serivce Mesh (https://github.com/openservicemesh/osm/)~~
- Otomi - PaaS (https://github.com/redkubes/otomi-core) -promote
- ~~Rook - Storage Orchestration (https://github.com/rook/rook)~~
- ~~Stern - Multi pod and container log tailing (https://github.com/wercker/stern)~~

# zCoolGitOpsProjectsToTrack (created a list below for Github projects, used for cluster state)
- https://github.com/stars/antoinesylvia/lists/gitops-in-action

# zCertificationToAttain_2023/24 (Getting in lab time with a 2 and 4 year old at home isn't easy)
- Certified Kubernetes Administrator (CKA): https://www.cncf.io/certification/cka/
  - Booked!
  - Exam Prep Course: https://www.techworld-with-nana.com/kubernetes-administrator-cka ($$)
  - Github Resource: https://github.com/kmjayadeep/cka-learning
  - Github Resource: https://github.com/eon01/kubectl-SheetCheat

# zKubernetesOther
- Kubernetes Documentary Part 1 (https://www.youtube.com/watch?v=BE77h7dmoQU)
- Kubernetes Documentary Part 2 (https://www.youtube.com/watch?v=318elIq37PE)
