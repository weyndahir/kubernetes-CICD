Installing Prometheus and Grafana
wget https://get.helm.sh/helm-v3.2.4-linux-amd64.tar.gz
tar -xvf helm-v3.2.4-linux-amd64.tar.gz
sudo mv linux-amd64/helm /usr/bin/
sudo chmod +x /usr/bin/helm
helm version
----------------------------
Adding repo
helm repo add stable https://charts.helm.sh/stable
creating namespace
kubectl create ns prometheus
--------------------------
Note:
Grafan comes with prometheus installation:
helm install prometheus stable/prometheus-operator --namespace promethues
The Prometheus Operator has been installed. Check its status by running:
kubectl --n Prometheus get pods -l "release=prometheus"

---------------------------------------------------------------------

I am sure you need to access your dashboard over IP or DNS
use the following services to created nodePort, the both yaml files are added on this repo
Happy Grafana---

to get the user name and passord
kubectl get secret --namespace prometheus prometheus-grafana -o yaml
openssl base64 -d
YWRtaW4=
admin
openssl base64 -d
cHJvbS1vcGVyYXRvcg==
prom-operator
you can rename the password afterwards!
I hope someone will approciated!
