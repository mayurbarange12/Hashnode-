---
title: "Day 24 - Kubernetes Configuration Manifest File Using Deployment"
datePublished: Tue Jan 02 2024 12:32:08 GMT+0000 (Coordinated Universal Time)
cuid: clqwbx6zu000108jzgza17x10
slug: day-24-kubernetes-configuration-manifest-file-using-deployment
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704200570032/1052822d-a4ff-4e07-aa79-b9589bf42250.png
tags: trainwithshubham-tws-90daysofdevops-90daysofdevopschallenge-devops-devopscommunity-shubhamlondhe-automation-kubernetes-autoscaling-autohealing-microservices-kubernetescluster-kubelet-kubectl-orchestration-minikube-kubeadm-pod-kubernetesdeployment-kubernetespods-kubernetesservice-namespace-labels-selectors

---

# **<mark>Deployment</mark>**

Deployment means Desired State provides declarative updates for Pods and ReplicaSets.

A Deployment in Kubernetes is a resource that manages and maintains a set of identical pods, ensuring they run and scale as desired, allowing for easy updates and rollbacks of applications.

## **What is the difference between labels and selectors?**

* **<mark>Labels</mark>:-** Labels are key-value pairs attached to Kubernetes objects (like pods, services, deployments) to categorize and organize them based on various attributes or metadata. They don't have a specific functionality by themselves but are used for identification and grouping.
    
* **<mark>Selectors</mark>:-** Selectors are used to query or select objects based on their labels. They're expressions used to match labels on resources. For example, a deployment might use a selector to identify which pods it should manage based on their labels. Selectors are used for tasks like specifying which resources a service should route traffic to or which pods a deployment should manage.
    

In essence, labels are the tags attached to objects for classification, while selectors are the means to query and select those objects based on their labels.

**<mark>Master Node</mark>:-**

* `vim deployment.yml`
    

```bash
apiVersion: apps/v1
kind: Deployment
metadata:
  name: todo-deployment
  namespace: todo-app
  labels:
    app: todo-label
spec:
  replicas: 5
  selector:
    matchLabels:
      app: todo-label
  template:
```

* Esc:wq Enter
    
* `cat pod.yml`
    
* Copy from **pod.yml** and paste it in **deployment.yml** file.
    

```bash
metadata:
  name: todo-pod
  namespace: todo-app
spec:
  containers:
    - name: todo-ctr
      image: mayurbarange/node-app-test-new
      ports:
        - containerPort: 8000
```

**<mark>Final deployment.yml file</mark>:-**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704197554257/d16e723f-2967-4fa7-93df-5a0ada629ff3.png align="center")

* Esc:wq Enter
    
* `kubectl apply -f deployment.yml` --&gt; This command applies the configuration specified in "deployment.yml" to create or update a Kubernetes deployment.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704197597617/c2ed5707-e3a7-48bc-96fd-5c5862acf202.png align="center")

```bash
labels:
    app: todo-label
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704197652825/847e210e-8b0e-4d07-b83d-cbc4747aa6b6.png align="center")

* Esc:wq Enter
    
* `kubectl apply -f deployment.yml`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704197680010/7b4330ee-527e-46f7-ae11-0bfa0d8a705c.png align="center")

* `kubectl get pods -n todo-app`  --&gt; This command fetches and lists pods within the "todo-app" namespace in Kubernetes.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704197795764/5b0da2db-a238-4aa2-b755-2df60b257682.png align="center")

* `vim deployment.yml`
    

```bash
# Changed the replicas: 3 (desired state).
replicas: 3
```

* Esc:wq Enter
    
* `kubectl apply -f deployment.yml`
    
* `kubectl get pods -n todo-app`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704198052569/34dcd627-95b9-4355-8c40-bf7c86dff9aa.png align="center")