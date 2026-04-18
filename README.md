# kubernetes-tutorial

You will need minikube and something like docker desktop in order to get this project running.

You can get the application running by running the following commands
- minikube start --extra-config="apiserver.cors-allowed-origins=['http://boot.dev']"
- minikube dashboard --port=63840
    - keep this running
- kubectl create deployment synergychat-web --image=docker.io/bootdotdev/synergychat-web:latest
    - only need to run this once
- kubectl get pods
    - use the pod name for the following cmd e.g. synergychat-web-f7b9f96dd-ppqpc
- kubectl port-forward PODNAME 8080:8080
- kubectl proxy
