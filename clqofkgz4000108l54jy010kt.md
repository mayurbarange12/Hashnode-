---
title: "Day 22 - Kubernetes Installation Guide for Minikube and Kubeadm"
datePublished: Wed Dec 27 2023 23:52:04 GMT+0000 (Coordinated Universal Time)
cuid: clqofkgz4000108l54jy010kt
slug: day-22-kubernetes-installation-guide-for-minikube-and-kubeadm
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1703718278644/498d433f-e2d2-4053-bdef-9130d29fc917.png
tags: trainwithshubham-tws-90daysofdevops-90daysofdevopschallenge-devops-devopscommunity-shubhamlondhe-automation-kubernetes-autoscaling-autohealing-microservices-kubernetescluster-kubelet-kubectl-orchestration-minikube-kubeadm-pod

---

## **<mark>Minikube Installation Guide for Ubuntu</mark>:-**

**<mark>Minikube</mark>:-** Minikube is a tool that allows you to run a single-node Kubernetes cluster locally for development and testing purposes.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703718439978/67963e46-ae25-4baa-9430-8a792e173d7b.png align="center")

* Create an EC2 Instance named as "**minikube-server**" -&gt; AMI: "**Ubuntu"** -&gt; Instance type: "**t2.medium"** -&gt; Launch instance.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703718514659/1d3f145d-2277-49e2-9c6e-f65519ea6618.png align="center")

* `sudo apt update`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703718543215/215757e9-66d8-4535-b06a-818adab352e7.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703718550253/13cbd107-1ac8-4505-8d77-72496873aca7.png align="left")

* `sudo apt install -y curl wget apt-transport-https`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703718575898/4e605af9-6b61-4834-a0b4-fbca51e926b2.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703718599604/77903d0d-4ef7-41f7-858b-40166cc6635e.png align="center")

* `sudo apt install -y docker.io`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703718622146/6269fa49-15bf-42da-9427-bdc1e4496677.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703718648287/f2301ec6-2744-480c-b706-8ed7ba00f1e1.png align="center")

* `sudo systemctl start docker`
    
* `sudo systemctl enable docker`  --&gt; If the system will restart then automatically docker will be start.
    
*  `sudo usermod -aG docker $USER && newgrp docker` --&gt;Add current user to docker group.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703718795339/ac25f3d6-e3b2-42c3-bdf2-c118c6f4fd05.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703718802563/c6450641-bd88-4978-826e-f8d4d6ca31b8.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703718806522/c5437ff8-c86f-4f4f-b2ba-ec0c3ad531fd.png align="center")

* `curl -Lo minikube` [`https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64`](https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64)
    
* `chmod -x minikube`
    
* `sudo mv minikube /user/local/bin/`
    
* `minikube`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703718854114/74c04596-c2a5-445b-acf5-984e3c491096.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703718859993/2ed74f20-5360-4670-8964-40b381cc6f15.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703718865580/ff900310-3933-491f-957b-1a80d8acf498.png align="center")

* `curl -LO "`[`https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl`](https://dl.k8s.io/release/$(curl%20-L%20-s%20https:/dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl)`"`
    
* `chmod +x kubectl`
    
* `sudo mv kubectl /usr/local/bin/`
    
* `kubectl`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703718908047/980d38e1-4469-4011-8c4b-23c47ae2ca7e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703718911715/67bc6b60-d4a7-4533-bb75-894a4c35795d.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703718917414/32693480-fb6c-4e75-8418-0797d58b6e21.png align="center")

* **minikube start --driver=docker**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703718946960/f8e4bf21-aac9-4656-8b12-4c64a7779761.png align="center")

* `docker ps`
    
* `minikube ssh`  \--&gt; Allows you to SSH into the Minikube VM, giving you direct access to the Minikube's host environment for advanced troubleshooting or configuration purposes.
    
* `docker ps`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703719081054/1e9c82ad-4f78-4a51-8a45-3f42029d5120.png align="center")

* exit
    
* `kubectl get nodes`  \--&gt; Retrieves a list of all nodes in the Kubernetes cluster, displaying their status and other relevant information.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703719155438/2eea45b7-3eaf-4fc0-8341-50fe634e838a.png align="center")

## **<mark>Kubeadm Installation Guide for Ubuntu</mark>:-**

**<mark>Kubeadm</mark>:-** It is a command-line tool used to bootstrap, set up, and manage Kubernetes clusters.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703719349629/2a376ed1-515e-4ae8-b9fa-72154a917cea.png align="center")

* Create an EC2 Instance named as "**kubernetes-master**" -&gt; AMI: "**Ubuntu"** -&gt; Instance type: "**t2.medium"** -&gt; Number of Instances: **2** -&gt; Launch instance.
    
* Open both the instances in separate webpage.
    
* **First instance** rename as "**kubernetes-master**"
    
* **Second instance** rename as **"kubernetes-worker"**
    

**<mark>Container Runtime Interface</mark>:-** The Container Runtime Interface (CRI) is a standardized interface in Kubernetes that enables communication between the kubelet (node agent) and container runtimes, allowing different runtimes like Docker, containerd, or others to be used interchangeably within the cluster.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703719449878/2ff639ed-3312-40de-93f4-7b2996741a40.png align="center")

**<mark>Firstly will setup Master Node</mark>:**\-

* `sudo su`
    
* `apt update -y`
    
* `apt install` [`docker.io`](http://docker.io) `-y`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703719516899/64b3c0e5-aa40-4225-9236-caa82e3031f2.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703719521999/5a2d6301-d2bc-4e9f-838a-4474e82ac126.png align="center")

* `systemctl start docker`
    
* `systemctl enable docker`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703719547843/cf598e44-c94c-40f3-993e-4ec1c833f46a.png align="center")

**Adding GPG Keys:-**

* `curl -fsSL "`[`https://packages.cloud.google.com/apt/doc/apt-key.gpg`](https://packages.cloud.google.com/apt/doc/apt-key.gpg)`" | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/kubernetes-archive-keyring.gpg`
    

**Add the repository to the sourcelist:-**

* `echo 'deb` [`https://packages.cloud.google.com/apt`](https://packages.cloud.google.com/apt/doc/apt-key.gpg) `kubernetes-xenial main' | sudo tee /etc/apt/sources.list.d/kubernetes.list`
    
* `apt update -y`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703719619892/2c28a1ce-5b87-40f0-b7c2-8267a4b40a96.png align="center")

* `apt install kubeadm=1.20.0-00 kubectl=1.20.0-00 kubelet=1.20.0-00 -y`   \--&gt; Installing kubeadm, kubectl and kubelet
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703719648775/0ff80b00-1b54-4534-a3ed-0201e8fe9bc9.png align="center")

**<mark>Now will setup worker node</mark>:-**

* `sudo su`
    
* `apt update -y`
    
* `apt install` [`docker.io`](http://docker.io) `-y`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703719709831/634404d9-e50d-4e04-bbf4-935b10fb9d6f.png align="center")

* `systemctl start docker`
    
* `systemctl enable docker`
    

 **Adding GPG Keys:-**

* `curl -fsSL "`[`https://packages.cloud.google.com/apt/doc/apt-key.gpg`](https://packages.cloud.google.com/apt/doc/apt-key.gpg)`" | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/kubernetes-archive-keyring.gpg`
    

**Add the repository to the sourcelist:-**

* `echo 'deb` [`https://packages.cloud.google.com/apt`](https://packages.cloud.google.com/apt/doc/apt-key.gpg) `kubernetes-xenial main' | sudo tee /etc/apt/sources.list.d/kubernetes.list`
    
* `apt update -y`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703719796357/a0df87b8-bcec-4e18-b09a-fe16d4df8478.png align="center")

* `apt install kubeadm=1.20.0-00 kubectl=1.20.0-00 kubelet=1.20.0-00 -y`   \--&gt; Installing kubeadm, kubectl and kubelet
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703719836882/2a726fc7-149f-41ab-87d4-3f0c579c4cdc.png align="center")

**<mark>Master node</mark>:-**

1. **Initialize the Kubernetes master node:-**
    

* `kubeadm init`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703719903181/f1795ed0-fe55-4327-99d5-3e7de804d532.png align="center")

**After successfully running, your Kubernetes control plane will be initialized successfully.**

1. **Set up local kubeconfig (both for root user and normal user):-**
    

**To start using your cluster, you need to run the following as a regular user:**

(First Exit then below commands needs to run)

* `mkdir -p $HOME/.kube`
    

* `sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config`
    
* `sudo chown $(id -u):$(id -g) $HOME/.kube/config`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703720127327/71759868-91da-4061-898c-d3f584cf0bbb.png align="center")

* `cat /etc/kubernetes/admin.conf`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703720159412/3da77b89-e3df-4ff0-aaa7-7ba3f08a6a19.png align="center")

1. **Apply Weave Network:-**
    

* `kubectl apply -f` [`https://github.com/weaveworks/weave/releases/download/v2.8.1/weave-daemonset-k8s.yaml`](https://github.com/weaveworks/weave/releases/download/v2.8.1/weave-daemonset-k8s.yaml) --&gt; Weave Network will establish.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703720272328/40bcb33a-9e3a-4593-8680-a36280d7a6b0.png align="center")

**<mark>Worker Node</mark>:-**

1. **Run the following commands on the worker node:-**
    

* `sudo su`
    
* `sudo kubeadm reset pre-flight checks`  \--&gt; The command "sudo kubeadm reset" performs pre-flight checks to ensure the system is ready for the cluster reset, validating prerequisites and configurations before executing the reset operation.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703720366572/c0bde5cd-da9f-4ea4-a0b3-59ec401137d4.png align="center")

**<mark>Master Node</mark>:-**

* **kubectl get nodes** \--&gt; Retrieves a list of all nodes in the Kubernetes cluster, displaying their status and other relevant information.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703720417969/bdd2dc21-f793-4d99-ba0a-185aefc8c035.png align="center")

**Generate a token for worker nodes to join:-**

* `sudo kubeadm token create --print-join-command` --&gt; The command generates a token used for nodes to join the Kubernetes cluster and prints the associated join command.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703720528554/59029296-cf03-4fbd-a5fb-021d38a7ea6d.png align="center")

* **Expose port 6443 in the Security group for the Worker to connect to Master Node:-**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703720569840/bd86e4ba-20c9-4583-9748-e2f93a285077.png align="center")

**<mark>Worker Node</mark>:-**

* Paste the join command you got from the master node and append --v=5 at the end. Make sure either you are working as sudo user or use sudo before the command:-
    
* `kubeadm join 172.31.53.171:6443 --token 5xsky4.pgu1e1sbvno269av     --discovery-token-ca-cert-hash sha256:846234ead25499bf807dbf1e1270a59ef220a0d023e311f9195a903de386a5f8`
    
* `kubeadm join 172.31.53.171:6443 --token 5xsky4.pgu1e1sbvno269av     --discovery-token-ca-cert-hash sha256:846234ead25499bf807dbf1e1270a59ef220a0d023e311f9195a903de386a5f8`
    
    `--v=5`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703720686056/10c303f1-4056-4bd0-822c-3ea7c9b7f60e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703720689945/6f227e86-bcdb-411d-81ba-eb08d0e7f7e3.png align="center")

**<mark>Master Node</mark>:-**

* `kubectl get nodes`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703720719128/cec44937-435b-4da1-9887-b0ebe01ff9b1.png align="center")

### **<mark>Pod</mark>:-**

A pod in Kubernetes is the smallest deployable unit that consists of one or more containers sharing storage, networking, and an IP address, representing a single instance of an application or a group of tightly coupled applications.

* `kubectl get pods` \--&gt; Retrieves a list of pods running in the current namespace, displaying their status, names, and other relevant information.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703720769678/9be0aa21-2fe3-4599-9b79-ac2c7f426da9.png align="center")

* `kubectl run nginx --image=nginx`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703720900423/49d2ff5c-0536-4d29-aeb7-2f9dd42ee22f.png align="center")

**<mark>Worker Node</mark>:-**

* `sudo docker ps`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703720926721/27c8483e-48e6-45e3-8a26-1123bc0b87d5.png align="center")

**<mark>Master Node</mark>:-**

* `kubectl get pods`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703720966485/f3a83dc2-eaf1-423a-af23-59b3cbb233c5.png align="center")