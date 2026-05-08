# kubernetes-tutorial

You will need minikube and something like docker desktop in order to get this project running.

You can get the application running by running the following commands


## Setup

Firstly setup your /etc/hosts to have the following lines

127.0.0.1        synchat.internal
127.0.0.1        synchatapi.internal

For WSL you will need to change it here `C:\Windows\System32\drivers\etc\hosts`

Then you can run the following commands

- minikube start --extra-config="apiserver.cors-allowed-origins=['http://boot.dev']"
- kubectl create deployment synergychat-web --image=docker.io/bootdotdev/synergychat-web:latest
    - only need to run this once

## Useful commands
- kubectl get pods
    - use the pod name for the following cmd e.g. synergychat-web-f7b9f96dd-ppqpc
- kubectl delete pod {podname}
- kubectl port-forward PODNAME 8080:8080
- minikube dashboard --port=63840
- kubectl apply -f {filename}
- kubectl proxy
- kubectl get deployment synergychat-web -o yaml > web-deployment.yaml
- minikube tunnel -c
