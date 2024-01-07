---
title: "Day 27 - Kubernetes Configuration Manifest File Using Persistent Volume & Persistent Volume Claim"
datePublished: Sun Jan 07 2024 17:15:20 GMT+0000 (Coordinated Universal Time)
cuid: clr3r8my7000109l9f2bebq4q
slug: day-27-kubernetes-configuration-manifest-file-using-persistent-volume-persistent-volume-claim
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704647678541/57843392-c6c3-47e0-ab5b-debb1f32ece8.png
tags: trainwithshubham-tws-90daysofdevops-90daysofdevopschallenge-devops-devopscommunity-shubhamlondhe-automation-kubernetes-autoscaling-autohealing-microservices-kubernetescluster-kubelet-kubectl-orchestration-minikube-kubeadm-pod-kubernetesdeployment-kubernetespods-kubernetesservice-namespace-labels-selectors-nodeport-clusterip-loadbalancer-autoscaling-autohealing-configmaps-secrets-persistentvolume-persistentvolumeclaim

---

## **PersistentVolume (PV):**

In Kubernetes, a PersistentVolume is a storage abstraction that represents a piece of storage in the cluster, such as a physical disk, network storage, or cloud storage. It exists independently of any Pod and can be dynamically provisioned or statically defined by a cluster administrator. PVs have lifecycle independent of Pods and are provisioned using storage classes.

## **PersistentVolumeClaim (PVC):**

A PersistentVolumeClaim is a request made by a user (in the form of a Kubernetes object) for storage resources from a PersistentVolume. It acts as a request for storage by a user or a Pod. When a user creates a PVC, Kubernetes finds an appropriate PV that satisfies the PVC requirements based on capacity, access mode, and other parameters defined in the claim.

 In essence, PersistentVolumes represent actual storage resources in the cluster, while PersistentVolumeClaims act as a way for applications (Pods) to request and use these storage resources without having to know the details of the underlying storage infrastructure. PVs and PVCs help decouple storage provisioning from Pod lifecycle management in Kubernetes.

* **<mark>Stateless</mark>:-** In Stateless app no need to attach any storage.
    
* **<mark>Stateful</mark>:-** In Stateful app need to attach storage/disk.
    

### **Why Persistent Volume in Kubernetes called "PersistentVolume" and "PersistentVolumeClaim" terms?**

* Think of a "**PersistentVolume**" in Kubernetes as a special storage area that sticks around even if no one is using it right now. It's like having a storage unit or a locker that stays there in a building, ready for someone to use whenever they need it. This storage space can be a hard drive, cloud storage, or any kind of storage that Kubernetes manages.
    
* So, even if no application or program is using this space at the moment, it's ready and waiting—**persistent**, just like a storage unit that's always available even if no one's currently renting it. When an application needs some storage, it can ask for a chunk of this persistent storage using what's called a "**PersistentVolumeClaim**" and Kubernetes will provide it with a piece of this persistent storage it requested.
    

### **We are creating PersistentVolume.yml file:-**

**<mark>Worker Node</mark>:-**

* `mkdir volume`
    
* `cd volume/`
    
* `pwd`
    

`/home/ubuntu/volume`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704646698350/e1ba70ed-488b-4445-84e2-e0614e84ce1f.png align="center")

**<mark>Master Node</mark>:-**

* `cd projects/`
    
* `cd mysql/`
    
* `vim persistentVolume.yml`
    

```bash
apiVersion: v1
kind: PersistentVolume
metadata:
  name: mysql-pv-volume
  namespace: mysql
  labels:
    app: mysql
spec:
  storageClassName: manual
  capacity:
    storage: 2Gi
  accessModes:
    - ReadWriteOnce
  hostPath:
    path: "/home/ubuntu/volume"
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704646715511/dc7413fc-b3a2-41cb-b8aa-a6118ecb2bb8.png align="center")

* Esc:wq Enter
    
* `kubectl apply -f persistentVolume.yml`
    
* `kubectl get pv -n mysql`   **--&gt; RWO(ReadWriteOnce)**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704646887160/9b41b7cf-fac5-4bc7-8635-2f3355633038.png align="center")

### **What all reclaim policies are available in PersistentVolume of Kubernetes?**

* **<mark>Retain</mark> -** Keeps the storage even after the claim that uses it is deleted, requiring manual cleanup.
    
* **<mark>Delete</mark> -** Automatically removes the storage asset when the claim using it is deleted.
    
* **<mark>Recycle (Deprecated)</mark> -** Tries to clean the volume by deleting its contents but doesn't free the underlying storage.
    
* **<mark>External</mark> -** Assumes an external entity manages the volume's lifecycle, reconnecting it when needed in the cluster.
    

### **We are creating PersistentVolumeClaim.yml file:-**

**<mark>Master Node</mark>:-**

* `vim persistentVolumeClaim.yml`
    

```bash
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: mysql-pv-claim
  namespace: mysql
spec:
  storageClassName: manual
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 1Gi
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704647102663/ee4cb69c-b5a9-4377-810f-3f3fc07a7d6c.png align="center")

* Esc:wq Enter
    
* `kubectl apply -f persistentVolumeClaim.yml`
    
* `kubectl get pvc -n mysql`  \--&gt; Now persistentVolumeClaim is Bounded with persistentVolume.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704647137830/44ae852e-9a9e-40c9-9627-f6e74b39615a.png align="center")

### **We are attaching PersistentVolume with the Deployment file:-**

**<mark>Master Node</mark>:-**

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
            - name: MYSQL_ROOT_PASSWORD
              valueFrom:
                secretKeyRef:
                  name: mysql-secret
                  key: MYSQL_PASSWORD
          volumeMounts:                 
            - name: mysql-persistent-storage
              mountPath: /var/lib/mysql
      volumes:                
        - name: mysql-persistent-storage
          persistentVolumeClaim:
            claimName: mysql-pv-claim
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704647345660/12eca704-6d27-42c3-b3f7-b4da577aeb2c.png align="center")

* Esc:wq Enter
    
* `kubectl apply -f deployment.yml`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704647362361/10e3eb99-1b95-49cd-9488-e3033e24d8f1.png align="center")

* `kubectl get deployment -n mysql`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704647381901/7e6c7e7f-356e-41f6-afc1-71000177876e.png align="center")

* `kubectl get pods -n mysql`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704647403361/62d01500-fddb-4bf9-87a0-375748993bcd.png align="center")

* `kubectl describe deployment mysql-deployment -n mysql`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704647429546/10d0e360-147b-4f4d-8a42-1c8a5e3f39cc.png align="center")

**<mark>Worker Node</mark>:-**

* `cd volume/`    
    
* `ls`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704647499788/080418bc-8dee-44a5-a0c8-716dc5ce0f59.png align="center")