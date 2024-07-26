**Installing K8s in Ec2**
-
- `Install Docker first.`
- For windows: [Click Here](https://storage.googleapis.com/minikube/releases/latest/minikube-installer.exe)
- `curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64`
- `sudo install minikube-linux-amd64 /usr/local/bin/minikube`


**Running flask through k8s**
-
- `minikube start`
- `eval $(minikube docker-env)`
- `docker build -t fimage:latest .`
- `kubectl apply -f flask-app-deployment.yaml`
- `kubectl get services`
- `minikube tunnel` 
 
