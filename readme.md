**Installing K8s in Ec2**
-
- `Install Docker first.` for windows [click here](https://desktop.docker.com/win/main/amd64/Docker%20Desktop%20Installer.exe?utm_source=docker&utm_medium=webreferral&utm_campaign=docs-driven-download-win-amd64)
- For windows: [Click Here](https://storage.googleapis.com/minikube/releases/latest/minikube-installer.exe)
- `curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64`
- `sudo install minikube-linux-amd64 /usr/local/bin/minikube`


**Running flask through k8s**
-
- `sudo su`
- `minikube start --force`
- `eval $(minikube docker-env)`
- `docker build -t flaskimage:latest .`
- `curl -LO "https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl"`
- `chmod +x ./kubectl`
- `mv ./kubectl /usr/local/bin/kubectl`
- `kubectl apply -f flask-app-deployment.yaml`
- `kubectl get services`
- `sudo apt update`
- `sudo apt install nginx`
- `sudo vim /etc/nginx/sites-available/default`
- Paste this `server {
    listen 80;
    server_name 13.233.212.12;

    location / {
        proxy_pass http://192.168.49.2:32077;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }
}
`
- `sudo systemctl restart nginx`
- Goto Your `Public IP Address of your Instance`

 
