Useful Info:
--
sometimes you need to remove or uninstall kubectl kubeadm kubelet
I find it's time consumming, so here are some steps you may needed:
1-	Remove kubectl kubelet kubeadm
2-	Re-install docker
	a.	Using 	curl -sSL https://get.docker.com/ | sh
	b.	Add pi user to the docker group sudo usermod –aG docker pi
	c.	Enable docker services by sudo systemctl enable docker
	d.	/proc/sys/net/bridge/bridge-nf-call-iptable reset to 1
	e.	Incase you need to remove docker running containers 
	i.	docker stop $(docker ps -a -q)
	ii.	docker rm $(docker ps -a -q)
	f.	
3-	Re-install kubelet kubectl kubeadm
4-	Create a user pi add to group docker useradd pi, groupadd pi, usermod –aG pi  pi
5-	Assign a password
6-	If you previousely run kubelet join
	a.	Run this kubeadm reset –force
	b.	You should add this one with join command --ignore-preflight-errors='DirAvailable--etc-kubernetes-manifests,FileAvailable--etc-kubernetes-kubelet.conf,Port-   
  10250,FileAvailable--etc-kubernetes-pki-ca.crt'

