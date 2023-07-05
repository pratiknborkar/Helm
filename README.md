# What is Helm

Helm is a tool that streamlines installing and managing Kubernetes applications. Think of it like Apt/Yum/Homebrew for K8S.
Helm uses a packaging format called charts. A chart is a collection of files that describe a related set of Kubernetes resources. 
A single chart might be used to deploy something simple, like a memcached pod, or something complex, like a full web app stack with 
HTTP servers, databases, caches, and so on.

## What is a Helm repository?

A Helm repository is a collection of Helm charts. Developers can upload charts to a Helm repository, and users can download them from there.
The ability to share charts using a repository is another advantage of Helm. Helm repositories make it easy for developers to share their 
applications with users, and for users to find the applications they need, in a centralized location. Without Helm repositories, users 
would be left to scour GitHub manually when looking for the charts they need to deploy applications on Kubernetes.

## Installation of helm

Helm Version 2.14.2
```
wget https://get.helm.sh/helm-v2.14.1-linux-amd64.tar.gz
tar zxf helm*gz
sudo cp linux-amd64/helm /usr/local/bin/
rm -rf helm* linux-amd64
kubectl -n kube-system create serviceaccount tiller
kubectl create clusterrolebinding tiller --clusterrole cluster-admin --serviceaccount=kube-system:tiller
helm init --service-account tiller
```

*Wait for tiller component to be active*

Helm Version 3.12.1
```
 curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
 chmod 700 get_helm.sh
 ./get_helm.sh
 
 ```
## New Location For Stable and Incubator Charts
For Helm 3.4
```
helm repo add stable https://charts.helm.sh/stable --force-update
```
For Helm 2.17

```
helm repo rm stable
helm repo add stable https://charts.helm.sh/stable
```
