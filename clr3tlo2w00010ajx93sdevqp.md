---
title: "Day 28 -  Kubernetes Helm"
datePublished: Sun Jan 07 2024 18:21:27 GMT+0000 (Coordinated Universal Time)
cuid: clr3tlo2w00010ajx93sdevqp
slug: day-28-kubernetes-helm
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704648970836/4e6caa4d-83a9-4b2b-842c-82b10e18a240.png
tags: trainwithshubham-tws-90daysofdevops-90daysofdevopschallenge-devops-devopscommunity-shubhamlondhe-automation-kubernetes-autoscaling-autohealing-microservices-kubernetescluster-kubelet-kubectl-orchestration-minikube-kubeadm-pod-kubernetesdeployment-kubernetespods-kubernetesservice-namespace-labels-selectors-nodeport-clusterip-loadbalancer-autoscaling-autohealing-configmaps-secrets-persistentvolume-persistentvolumeclaim-helm

---

## **HELM**

Helm is like an **app store/package** installer for Kubernetes, making it easy to find, share, and install applications using pre-configured templates called charts, simplifying complex deployments on Kubernetes.

* Helm is an open-source package manager for Kubernetes that automates the deployment of software for Kubernetes in a simple and consistent way.
    
* It uses a packaging format called charts, which is a collection of files that describe a related set of Kubernetes resources.
    
* Helm makes it easy to package applications for Kubernetes and deploy them using just a few commands.
    
* It is the K8s equivalent of yum or apt and includes all the necessary code and resources needed to deploy an application to a cluster.
    

### **How to Install helm in Ubuntu**

**<mark>Master Node</mark>:-**

* `curl` [`https://baltocdn.com/helm/signing.asc`](https://baltocdn.com/helm/signing.asc) `| gpg --dearmor | sudo tee /usr/share/keyrings/helm.gpg > /dev/null`
    
    `sudo apt-get install apt-transport-https --yes`
    
    `echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/helm.gpg]` [`https://baltocdn.com/helm/stable/debian/`](https://baltocdn.com/helm/signing.asc) `all main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list`
    
    `sudo apt-get update`
    
    `sudo apt-get install helm`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704649217871/b2ee92f6-4475-4554-9908-72f70cc2c412.png align="center")

* `cd projects/`
    
* `mkdir helm-tut`
    
* `cd helm-tut/`
    
* `helm create node-app`
    
* `cd node-app/`
    
* `ls`
    
* `cd templates/`
    
* `ls`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704649283358/768822e1-bf8d-4640-972f-0110f23b1f57.png align="center")

**<mark>Note</mark>:-**

**Templates:-** It will not change anything.

**Values.yaml file:-** In this file values will be change.

* `vim deployment.yaml` --&gt; Already it is created in **helm**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704649306499/2359c0fc-55c6-419e-ba23-38b6ee0542a0.png align="center")

* Esc:wq Enter
    
* `cd  ..`
    
* `vim Chart.yaml`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704649343362/fa9c0914-46f0-4631-93c4-779bfea53ae3.png align="center")

* `vim values.yaml`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704649376838/7f7de27d-5a86-4750-b77f-15408ec34589.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704649382959/a593b35f-53ec-40f1-9c42-f661125a1ba5.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704649387627/61ee53c5-34d3-44db-8e83-36922a240bc2.png align="center")

**<mark>Ingress</mark>:-**

In Kubernetes, Ingress manages external access to services within the cluster, acting as a traffic controller by routing incoming HTTP and HTTPS requests to the appropriate services based on defined rules and configurations.

* `cd ..`
    
* `helm install node-app ./node-app`
    
* `vim node-app/values.yaml`
    

```bash
autoscaling:
    enabled: false   #--> Make it false.
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704649492299/38668995-65ac-4a5c-935e-1b455baa35d0.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704649520567/8edeace7-f5ce-41e2-9031-67c052000033.png align="center")

* `helm install node-app ./node-app`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704649564500/e0966704-8cf7-4af3-b043-79eae213bf3b.png align="center")

* `kubectl get pods` --&gt; Nginx Image is Deployed through helm.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704649595291/afa7b25f-a55e-4986-8f80-08c52c6b0226.png align="center")

* `vim node-app/values.yaml`
    

```bash
service:
	type: NodePort
	port: 80
	targetPort: 80
	nodePort: 30009
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704650450064/a6031aa9-2baf-45e9-b428-46bbadacd304.png align="center")

* `vim node-app/templates/service.yaml`
    

```bash
targetPort: {{ .Values.service.targetPort }}

nodePort: {{ .Values.service.nodePort }}
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704650655407/6d0c0b7c-63dc-4040-83f6-031f45b861b9.png align="center")

* Esc:wq Enter
    
* `kubectl get svc` --&gt; Now node-app is in **ClusterIP** type.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704650701029/d2b1bd38-fd81-41ac-88d8-f696af601820.png align="center")

* `helm uninstall node-app`
    
* `helm install node-app ./node-app`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704650778548/baa7c6e8-e1e9-4f7b-8f81-67c10ac12375.png align="center")

* `kubectl get svc` --&gt; Now node-app is in **NodePort** type.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704650828853/ec3cba67-6f5c-4a6e-b737-9662dc3b22db.png align="center")

* Take "kubernetes-worker" EC2 --&gt; Public IP and type url in browser **\--&gt; 18.212.176.253:30009**
    

**Nginx Image is Deployed and Run through helm.**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704650882477/0b31191a-48d5-4d07-ad35-823b58763aff.png align="center")

### **Now We will change "Nginx Image" to my DockerHub Image "node-app-test-new"**

* `vim node-app/values.yaml` --&gt; Changes has been manually done.
    

```bash
repository: mayurbarange/node-app-test-new
tag: "latest"
 targetPort: 8000
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704650999151/004d7510-4d3b-4438-b742-82bc64973a67.png align="center")

* `helm uninstall node-app`
    
* `helm install node-app ./node-app`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704651075422/77c2b36b-b57d-4686-9c94-a3b706b8132a.png align="center")

* `kubectl get pods`   --&gt; Pod is Running but not Ready.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704651095868/2ac991ba-bef4-40c9-8d10-044ded2274d3.png align="center")

* `vim node-app/templates/deployment.yaml` --&gt; ContainerPort has been changed manually.
    

```bash
containerPort: {{ .Values.service.targetPort }}
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704651494443/b43d8932-bb91-48ec-930d-0281c74a6a1b.png align="center")

* Esc:wq Enter
    
* `helm upgrade node-app node-app/`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704651540143/61052dbc-8f8f-4ff3-9c57-9fb6f16e0361.png align="center")

* Take "kubernetes-worker" EC2 --&gt; Public IP and type url in browser **\--&gt; 18.212.176.253:30009**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704651584941/48e2b5d6-7358-4e37-b576-6e2889a9e5f2.png align="center")