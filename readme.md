**Installing K8s in Ec2**
-
- `Install Docker first.` for windows [click here](https://desktop.docker.com/win/main/amd64/Docker%20Desktop%20Installer.exe?utm_source=docker&utm_medium=webreferral&utm_campaign=docs-driven-download-win-amd64)
- For windows: [Click Here](https://storage.googleapis.com/minikube/releases/latest/minikube-installer.exe)
- `curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64`
- `sudo install minikube-linux-amd64 /usr/local/bin/minikube`


**Running flask through k8s**
-
- `sudo minikube start --force`
- `eval $(sudo minikube docker-env)`
- `docker build -t flaskimage:latest .`
- `kubectl apply -f flask-app-deployment.yaml`
- `kubectl get services`
- `minikube tunnel --cleanup` 
 
