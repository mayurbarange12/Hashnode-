---
title: "Day 26 - Kubernetes Configuration Manifest File Using ConfigMaps and Secrets"
datePublished: Sun Jan 07 2024 15:30:07 GMT+0000 (Coordinated Universal Time)
cuid: clr3nhbxr000208jufaqn2hk4
slug: day-26-kubernetes-configuration-manifest-file-using-configmaps-and-secrets
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704638065124/a3387333-5fcc-478e-85ca-1c84652451a8.png
tags: trainwithshubham-tws-90daysofdevops-90daysofdevopschallenge-devops-devopscommunity-shubhamlondhe-automation-kubernetes-autoscaling-autohealing-microservices-kubernetescluster-kubelet-kubectl-orchestration-minikube-kubeadm-pod-kubernetesdeployment-kubernetespods-kubernetesservice-namespace-labels-selectors-nodeport-clusterip-loadbalancer-autoscaling-autohealing-configmaps-secrets

---

# **ConfigMaps:-**

A Kubernetes manifest file using ConfigMaps defines configurations separately from the pod specifications, allowing for easy management and access to configuration data within the cluster.

A ConfigMap is an API object used to **store non-confidential data** in **key-value pairs**. Pods can consume ConfigMaps as **environment variables**, command-line arguments, or as configuration files in a volume.

A ConfigMap allows you to decouple environment-specific configuration from your container images so that your applications are easily portable.

# **Secrets:-**

Secrets in Kubernetes securely store sensitive information, such as passwords or tokens, separate from pod specifications, enhancing security and access control within the cluster.

* **Create kubeadm and configure master and worker node of t2.medium.**
    

**<mark>Master Node</mark>:-**

* `sudo su`
    
* `mkdir projects`
    
* `cd projects/`
    
* `mkdir mysql`
    
* `cd mysql/`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704638676262/0e7e1def-f0fe-4774-9ebe-34009a2b20af.png align="center")

**Now I will create kubernetes mysql deployment manifest File:-**

* `vim deployment.yml`
    

```bash
apiVersion: apps/v1
kind: Deployment
metadata:
  name: mysql-deployment
  namespace: mysql
  labels:
    app: mysql

spec:
  replicas: 1
  selector:
    matchLabels:
      app: mysql
  template:
    metadata:
      labels:
        app: mysql
    spec:
      containers:
        - name: mysql
          image: mysql:8
          ports:
            - containerPort: 3306
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704639016790/14c3f0db-5249-4ee1-ac2d-658793658f57.png align="center")

* Esc:wq Enter
    

### **<mark>--dry-run=client </mark> :-**

The "--dry-run=client" flag in Kubernetes allows users to simulate resource creation/update without actually persisting changes, validating configurations locally.

* `kubectl apply -f deployment.yml --dry-run=client`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704638855911/050ef702-446b-4def-8ad0-22b00cb5ba4d.png align="center")

* `kubectl create namespace mysql`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704639277827/b518251c-3562-499e-bbfe-380be445def7.png align="center")

* `kubectl apply -f deployment.yml`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704639302167/29e34568-d711-4366-b898-0b8874085d66.png align="center")

* `kubectl get pods -n mysql`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704639350546/2471b780-170a-4616-b184-1d112bc1f49d.png align="center")

### **<mark>What is CrashLoopBackOf</mark>?**

CrashLoopBackOff in Kubernetes signifies a container repeatedly failing to start and crashing immediately after launch, causing Kubernetes to continually restart it in a loop.

* `vim configMaps.yml`
    

```bash
apiVersion: v1
kind: ConfigMap
metadata:
  name: mysql-config
  namespace: mysql
  labels:
    app: mysql

data:
  MYSQL_DATABASE: "cooldb"
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704639665912/6b4545ae-651d-40e1-863e-40f26f075dc5.png align="center")

* Esc:wq Enter
    
* `kubectl apply -f configMaps.yml --dry-run=client`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704639692619/6edba29c-fc9b-477b-abcb-5ed0c184e9ff.png align="center")

* `kubectl apply -f configMaps.yml`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704639730672/d286e25e-705c-4d4f-a8ce-80a4148f1336.png align="center")

* `kubectl get configMaps -n mysql` \--&gt; This command retrieves and lists ConfigMaps within the "mysql" namespace in Kubernetes.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704639756650/b19ce24b-8c0d-4a1b-aa92-0bae71054bf3.png align="center")

* `vim deployment.yml`
    

```bash
apiVersion: apps/v1
kind: Deployment
metadata:
  name: mysql-deployment
  namespace: mysql
  labels:
    app: mysql

spec:
  replicas: 1
  selector:
    matchLabels:
      app: mysql
  template:
    metadata:
      labels:
        app: mysql
    spec:
      containers:
        - name: mysql
          image: mysql:8
          ports:
            - containerPort: 3306
          env:                  
            - name: MYSQL_DATABASE
              valueFrom:
                configMapKeyRef:
                  name: mysql-config
                  key: MYSQL_DATABASE
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704639832406/8a86323e-a876-4bb5-a810-55eac2264c7b.png align="center")

* Esc:wq Enter
    
* `kubectl get pods -n mysql`
    
* `kubectl apply -f deployment.yml`
    
* `kubectl get pods -n mysql`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704639889152/3f6ca4c8-29cb-4c84-9592-e68d83f9a3c0.png align="center")

* `vim secrets.yml`
    

```bash
apiVersion: v1
kind: Secret
metadata:
  name: mysql-secret
  namespace: mysql
  labels:
    app: mysql

data:
  MYSQL_PASSWORD:
```

* Esc:wq Enter
    
* Use online Encrypter "[base64encode.org](http://base64encode.org)" to Encrypt/Encode the Password: let say **"trainwithshubham"**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704639991578/ea4da24f-37a1-497f-b4b8-b6eb5b1f0e32.png align="center")

* `echo "dHJhaW53aXRoc2h1YmhhbQ==" | base64 -d`  **--&gt;** The command **decodes** the Base64 encoded string "**dHJhaW53aXRoc2h1YmhhbQ==**" back to its original form using the base64 utility with the `-d` flag.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704641191035/e5e646bc-438b-4d65-9e04-ea321f065378.png align="center")

### **<mark>Opaque</mark>:-**

"Opaque" in Kubernetes refers to a type of secret where data is stored as an arbitrary, undifferentiated blob without Kubernetes understanding its content or structure. \[**arbitrary user-defined data**\]

* `kubectl delete -f deployment.yml`
    
* `vim secrets.yml`
    

```bash
apiVersion: v1
kind: Secret
metadata:
  name: mysql-secret
  namespace: mysql
  labels:
    app: mysql
type: Opaque
data:
  MYSQL_PASSWORD: dHJhaW53aXRoc2h1YmhhbQ== 
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704640869011/a1147872-8d0e-4e9b-8f5e-d6a57bbfa80b.png align="center")

* `kubectl apply -f secrets.yml`
    
* `kubectl apply -f deployment.yml`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704640638799/93d74fa1-947f-4ce6-bc7c-5fcffeea0811.png align="center")

* `kubectl get pods -n mysql`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704641040843/4bf7a4e9-c00e-4f65-8e56-4c9c3fcae1cd.png align="center")

**<mark>Worker Node</mark>:-**

* `docker ps`
    
* `docker exec -it 747d2d08ed96 bash`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704641148370/c8a47619-8521-4600-8ea8-51290317e188.png align="center")

* `mysql -u root -p`
    
* Enter Password: **trainwithshubham**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704641260121/db4ebcb7-c92c-4508-93fc-0c1b5da17cd2.png align="center")

* `show databases;`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704641289958/485d7c9f-4178-4af2-b954-601c4a37f8bf.png align="center")

* **exit**
    
* **exit**