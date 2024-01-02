---
title: "Day 23 - Kubernetes Configuration Manifest File Using Pods"
datePublished: Tue Jan 02 2024 11:46:21 GMT+0000 (Coordinated Universal Time)
cuid: clqwaaasn000c08l140bi3yvn
slug: day-23-kubernetes-configuration-manifest-file-using-pods
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704195703283/26e5b554-496c-465f-a935-29170b660407.png
tags: trainwithshubham-tws-90daysofdevops-90daysofdevopschallenge-devops-devopscommunity-shubhamlondhe-automation-kubernetes-autoscaling-autohealing-microservices-kubernetescluster-kubelet-kubectl-orchestration-minikube-kubeadm-pod-kubernetesdeployment-kubernetespods-kubernetesservice

---

# **Kubernetes configuration manifest file:-**

A Kubernetes configuration manifest file is a YAML or JSON file describing the desired state of various resources, like applications or services, in your Kubernetes cluster. It specifies details such as the type of resource, its properties (like name, image, ports), and the desired number of replicas. Once applied using "**kubectl apply**", Kubernetes works to make the actual state match the defined state in the file, ensuring your applications run as intended.

In Kubernetes, various kinds of manifest files are used to define different types of resources:-

* **Pod:** Defines a group of one or more containers and their shared resources.
    
* **Deployment:** Describes a set of identical pods, managing their lifecycle and scaling.
    
* **Service:** Enables networking and load balancing to pods, providing a consistent way to access them.
    
* **Ingress:** Specifies rules for routing external HTTP(S) traffic to services within the cluster.
    
* **PersistentVolume and PersistentVolumeClaim:** Manage storage and its allocation to pods.
    

## **<mark>Namespace</mark>:-**

A Kubernetes namespace is a virtual cluster within a physical cluster, enabling resource isolation and organizing objects by providing a scope for names. It helps partition cluster resources, allowing multiple users or teams to share the same Kubernetes cluster securely.

In Kubernetes, there are primarily two types of namespaces:

* **Default namespaces**: Kubernetes creates some default namespaces like default, kube-system, and kube-public during cluster setup to manage core resources and services.
    
* **Custom namespaces**: Users can create their namespaces to organize and isolate resources for different projects, teams, or purposes within the cluster, improving security and resource management.
    

# **<mark>Pods</mark>:-**

A pod in Kubernetes is the smallest deployable unit that consists of one or more containers sharing storage, networking, and an IP address, representing a single instance of an application or a group of tightly coupled applications.

**<mark>Master Node</mark>:-**

* `kubectl create namespace todo-app` **\--&gt;** This command creates a new namespace named "todo-app" in Kubernetes.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704193413788/6c4a3144-a3bc-4a73-b7f1-c5875b7e1466.png align="center")

* `mkdir projects`
    
* `cd projects/`
    
* `mkdir todo-app`
    
* `cd todo-app/`
    
* `vim pod.yml`
    

```bash
apiVersion: v1
kind: Pod
metadat:
  name: todo-pod
  namespace: todo-app
spec:
  containers:
    - name: todo-ctr
      image: mayurbarange/node-app-test-new
      ports:
        - containerPort: 8000
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704193556826/78875c8d-2aa0-4da7-8a3f-572570876f2a.png align="center")

* `kubectl apply -f pod.yml`   **\--&gt;** \[-f = filename\]
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704193604140/73d36226-5041-40f6-8634-055622e39730.png align="center")

* `kubectl create -f pod.yml`  **\--&gt;** Creates Kubernetes resources specified in the "pod.yml" file within the cluster.
    
* `kubectl apply -f pod.yml` **\--&gt;** Applies the configurations defined in "pod.yml" to create or update Kubernetes resources within the cluster based on the file specifications.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704193806042/0d4a6462-8b96-44a4-9c3c-c8df9b657c75.png align="center")

* `kubectl get pods`  **\--&gt;** Retrieves and lists the pods currently running in the kubernetes cluster.
    
* `kubectl get pods -n todo-app` **\--&gt;** This command fetches and displays pods within the "**todo-app**" namespace in Kubernetes.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704194482536/2055fe7e-73a9-46bb-8fae-d401e4f25090.png align="center")

**<mark>Worker Node</mark>:-**

* **docker ps**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704194571325/97d5f502-55c7-4feb-975c-ba41d16079b1.png align="center")