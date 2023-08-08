## Let's Goooooooooooooooooo

### This is the arcitechture of KubeEdge
![under1](https://github.com/1Shubham7/understanding-KubeEdge/assets/116020663/1e52665f-db37-45b4-bed9-1c54b8b4472f)

## Tutorial

### You obviously must have Docker and Kubernetes

Start out with this (Istalling docker)

```
sudo apt install docker.io -y
```

and (enabling docker)

```
sudo systemctl enable docker
```

confirm

```
sudo systemctl status docker
```

Then >>

Step 1. Install Kind
```
curl -Lo ./kind "https://kind.sigs.k8s.io/dl/v0.11.1/kind-$(uname)-amd64"
```
```
chmod +x ./kind
```
```
sudo mv ./kind /usr/local/bin/kind
```

Step 2. Install kubectl

```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```

```
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```

Step 5. Create a cluster using Kind
```
kind create cluster
```

To know about the cluster port -
```
kubectl cluster-info --context kind-kind
```
