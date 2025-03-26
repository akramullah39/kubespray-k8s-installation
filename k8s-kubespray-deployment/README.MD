 Installation via Kubespray

## Prerequisites
- Ubuntu 22.04 VM (4 vCPU, 8GB RAM, 20GB Disk)
- Ansible 2.12+
- Python 3.8+

## Step-by-Step Installation

### 1. Clone Kubespray. Here we are directly cloning the v2,22,2

git clone -b v2.22.2 https://github.com/kubernetes-sigs/kubespray.git

#From BASH Configure Inventory
Edit inventory/my-cluster/hosts.yaml:

## Run Installation
ansible-playbook -i inventory/mycluster/hosts.yml \
  --become \
  --become-user=root \
  --become-method=sudo \
  cluster.yml

## Verify Cluster

kubectl get nodes
kubectl get pods -A


