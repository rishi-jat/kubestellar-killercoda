# Prerequisites

Core prerequisites (Docker, kubectl, KubeFlex, clusteradm, Helm) and kind are required.

Run automated prerequisite check:

```bash
curl -fsSL https://raw.githubusercontent.com/kubestellar/kubestellar/refs/heads/main/scripts/check_pre_req.sh | bash
```{{exec}}

If tools are missing, install:

```bash
# Docker
curl -fsSL https://get.docker.com -o get-docker.sh && sudo sh get-docker.sh

# kubectl
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl" && chmod +x kubectl && sudo mv kubectl /usr/local/bin/

# kind
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.20.0/kind-linux-amd64 && chmod +x ./kind && sudo mv ./kind /usr/local/bin/kind

# Helm
curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash

# KubeFlex
bash <(curl -s https://raw.githubusercontent.com/kubestellar/kubeflex/main/scripts/install-kubeflex.sh) --ensure-folder /usr/local/bin --strip-bin

# clusteradm
bash <(curl -L https://raw.githubusercontent.com/open-cluster-management-io/clusteradm/main/install.sh) 0.10.1
```{{copy}}

<!-- TODO: Confirm Docker and kind function in Killercoda ubuntu environment -->
