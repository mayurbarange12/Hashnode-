---
title: "Day 25 - Kubernetes Configuration Manifest File Using Service"
datePublished: Tue Jan 02 2024 14:29:52 GMT+0000 (Coordinated Universal Time)
cuid: clqwg4lkp000208l8cks2bekz
slug: day-25-kubernetes-configuration-manifest-file-using-service
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704204529640/329595fb-fe79-4197-8249-97bc12923942.png
tags: trainwithshubham-tws-90daysofdevops-90daysofdevopschallenge-devops-devopscommunity-shubhamlondhe-automation-kubernetes-autoscaling-autohealing-microservices-kubernetescluster-kubelet-kubectl-orchestration-minikube-kubeadm-pod-kubernetesdeployment-kubernetespods-kubernetesservice-namespace-labels-selectors-nodeport-clusterip-loadbalancer-autoscaling-autohealing

---

# **Service**

A Kubernetes Service provides a consistent way to access and communicate with a group of pods, ensuring a stable endpoint for applications within the cluster.

In Kubernetes, there are mainly three types of services:

* **<mark>NodePort</mark>** **\-** Exposes the service on a static port on each node's IP, allowing access from outside the cluster.(**Range= 30000-32767**)
    
* **<mark>ClusterIP</mark> -** Exposes the service on an internal IP in the cluster, only accessible within the cluster.
    
* **<mark>LoadBalancer</mark> -** Assigns a public IP and routes external traffic to the service, typically used in cloud environments.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704202189723/d6bcd1fd-4955-4336-a0de-5b9d85ff04bb.png align="center")

* `vim service.yml`
    

```bash
apiVersion: v1
kind: Service
metadata:
  name: todo-service
  namespace: todo-app

spec:
  selector:
    app: todo-label
  type: NodePort
  ports:
    - port: 80    
      targetPort: 8000  
      nodePort: 30007
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704202273353/13a0fb58-9a2c-4af4-996c-4f660518c515.png align="center")

* `kubectl apply -f service.yml`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704202291225/4e43b0ee-f771-42ff-87fb-cbe3795e70eb.png align="center")

* `kubectl get svc -n todo-app` --&gt; This command fetches information about services within the "**todo-app**" namespace in Kubernetes. \[**svc = service**\]
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704202364307/70bf8b84-9b41-4174-87c9-ad4f5d1d7c49.png align="center")

* **Expose port 30007 in the Security group for the Master Node**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704202403406/91280cec-8e3a-4391-8f74-0f012c66c432.png align="center")

* **Take "kubernetes-worker" instance Public IP  and paste it in Browser --&gt; 100.26.122.8:30007 --&gt; Application is deployed using kubernetes.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704202439704/fadd515d-99ca-4b5c-bdd9-4be9a8af1a6e.png align="center")

**<mark>Master Node</mark>:-**

* `kubectl get pods -n todo-app`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704202483277/dda3c5f7-729b-4ca2-a347-de8be214d541.png align="center")

### **<mark>Autohealing</mark>**

Auto-healing in Kubernetes refers to the automatic detection and recovery from failures or issues within the cluster. Kubernetes continuously monitors the state of applications and infrastructure components. If it detects any failures, such as container crashes or node unavailability, it automatically takes actions to restore the desired state, like restarting containers or rescheduling pods onto healthy nodes. This process helps maintain the desired state of applications and ensures high availability without manual intervention.

* `kubectl delete pod todo-deployment-689d9dddf9-8jcpz -n todo-app`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704202538337/90b7c8bb-8470-436b-ab72-31b4add89ea6.png align="center")

* `kubectl delete pod todo-deployment-689d9dddf9-rpwgz -n todo-app`
    
* `kubectl get pods -n todo-app` **\--&gt; Here specific pod get deleted and auto-healed and the application is still running.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704202617464/d2315d42-e497-47b7-b71f-78a870e20b58.png align="center")

* **Still, my application is running...**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704202643485/bbf870e7-e979-4c70-872b-a9c57b400a4c.png align="center")

* `kubectl get deployment -n todo-app`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704204618715/b407fd80-f242-4bb9-ad8c-00e91a9548ec.png align="center")

### **<mark>Autoscaling</mark>**

Autoscaling in Kubernetes is the capability to automatically adjust the number of running pods within a cluster based on predefined metrics like CPU usage or custom metrics, ensuring efficient resource utilization and maintaining desired performance without manual intervention.

There are two main types:

1.**Horizontal Pod Autoscaler (<mark>HPA</mark>)**: Scales the number of pods based on CPU utilization or custom metrics, ensuring optimal performance by adding or removing pods as needed.

2.**Vertical Pod Autoscaler (<mark>VPA</mark>)**: Adjusts the resources allocated to individual pods, such as CPU and memory, based on actual usage to optimize efficiency.

* `kubectl scale deployment todo-deployment --replicas=5 -n todo-app` --&gt; This command scales the "todo-deployment" in the "todo-app" namespace to have **five** replicas, managing five instances of the associated pods.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704204660951/c1a3c323-15da-452f-b14b-54ddb27c913e.png align="center")

* `kubectl get pods -n todo-app` **\--&gt; Here pods get auto-scaled up=5**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704204677827/cb1191dc-83c3-4385-8606-50eac2023489.png align="center")