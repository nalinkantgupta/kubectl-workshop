# k8-cli-workshop

## Prerequisites utilitiea

```yaml
1. Jq.    (brew install jq)
2. Minikube.  (https://minikube.sigs.k8s.io/docs/start/)
3. Iterm2 terminal  (https://iterm2.com/downloads.html)
4. Oh-my-sh (https://ohmyz.sh/#install)
5. Git command  (https://git-scm.com/download/mac)
6. colordiff.  (brew install colordiff)
7. k(https://kubernetes.io/docs/tasks/tools/)
```

## Terminal Hack

### Install oh-my-zsh

```yaml
##  Installing omz
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

alias k=kubectl

```

## Enhance vim

```yaml
https://github.com/amix/vimrc#how-to-install-the-basic-version
```

## Minikube k

```yaml
brew install minikube
```

## Minikube Start Server

```yaml
minikube start
# minikube start --kubernetes-version=v1.20.2 --extra-config=apiserver.authorization-mode=RBAC
# minikube addons enable metrics-server
# minikube addons enable volumesnapshots
# minikube addons enable csi-hostpath-driver
# minikube addons enable ingress
# minikube addons enable dashboard
# minikube addons list
```

## Workshop

[Namespaces, Pods, Deployment file](workshop-1/1.md)

[Deploy and Scale an APP file](workshop-2/2.md)

[Secret & Patch  file](workshop-3/3.md)

[Level Up - troubleshooting file](Level-up/troubleshooting.md)
