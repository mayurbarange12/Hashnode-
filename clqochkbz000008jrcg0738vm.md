---
title: "Day 21 - Kubernetes Fundamentals"
datePublished: Wed Dec 27 2023 22:25:49 GMT+0000 (Coordinated Universal Time)
cuid: clqochkbz000008jrcg0738vm
slug: day-21-kubernetes-fundamentals
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1703688882629/47926a10-b58e-464e-bd87-55648a2d2818.jpeg
tags: trainwithshubham-tws-90daysofdevops-90daysofdevopschallenge-devops-devopscommunity-jenkins-cicdpipelines-cicd-jenkinsagent-shubhamlondhe-automation-kubernetes-autoscaling-autohealing-microservices-kubernetescluster-kubelet-kubectl-orchestration

---

# What is Kubernetes?

* Kubernetes is an open-source container management tool that automates container deployment, scaling and load balancing.
    
* It schedules, runs, and manages isolated containers that are running on virtual/physical/cloud machines.
    
* All top cloud providers support Kubernetes.
    
* One popular name for Kubernetes is k8s.
    

## **History of Kubernetes**

* Google developed an internal system called '**Borg**' (later named Omega) to deploy and manage thousands of Google applications and services on their cluster.
    
* In 2014, google introduced Kubernetes an open-source platform written in '**Golang**' and later donated to CNCF(**Cloud Native Computing Foundation**).
    

## **Features of Kubernetes**

* Orchestration (Clustering of any number of containers running on a different network)
    
* Autoscaling (Vertical & Horizontal)
    
* Auto Healing
    
* Load Balancing
    
* Platform Independent (Cloud/Virtual/Physical)
    
* Fault Tolerance (Node/POD/Failure)
    
* Rollback (Going back to the previous version)
    
* Health monitoring of containers
    
* Batch execution (One time, Sequential, Parallel)
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703714303808/a7f74820-fbff-40f4-8fed-5700852453c6.png align="center")

**Monolithic** - Deploying an application as a single, undivided unit without breaking it down into smaller, more manageable components or microservices.

**Microservices** - An architectural approach where applications are built as a collection of small, independent, and loosely coupled services, managed and orchestrated within a Kubernetes cluster for scalability and flexibility.

## **Architecture of Kubernetes**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703714672977/a8ddfc4f-69d4-47a6-8446-b07f617245b1.png align="center")

**Cluster:-** A cluster in Kubernetes is a set of nodes that collectively run containerized applications and are managed by the Kubernetes master.

 **Kubectl:-** kubectl is the command-line tool used to interact with Kubernetes clusters. It allows users to deploy and manage applications, inspect and manage cluster resources, view logs, execute commands within containers, and perform various administrative tasks within a Kubernetes cluster.

 **Scheduler:-** In Kubernetes, the scheduler is a component responsible for assigning newly created pods to nodes within the cluster based on resource requirements, policies, and constraints.

 **etcd:-** etcd stands for "extended distributed key-value store" etcd is a distributed key-value store used by Kubernetes to store its configuration data, acting as the cluster's reliable source of truth for information about the cluster state.

 **Controller Manager:-** The Controller Manager in Kubernetes is a component that manages various controllers responsible for maintaining the desired state of the cluster's resources.

 **API Server:-** The API Server in Kubernetes acts as the primary management point that handles API requests, validates and processes them, and interacts with the cluster's etcd datastore.

 **Kubelet:-** Kubelet is an essential node agent in Kubernetes responsible for managing and maintaining individual nodes in the cluster, ensuring containers are running as specified by the Kubernetes manifests.

 **Service Proxy:-** The service proxy in Kubernetes is responsible for routing and load-balancing incoming traffic to the appropriate pods within the cluster based on defined services.

 **CNI Network:-** A CNI (Container Network Interface) in Kubernetes is a plugin model that enables different container runtimes to set up and manage networking for pods and containers within the cluster.

## **Why do we write k8s?**

The term "Kubernetes" originates from Greek, meaning "helmsman" or "pilot." It's often abbreviated as "k8s" because it has eight letters between 'k' and 's'. This shorthand notation streamlines communication and saves typing effort, especially in documentation, discussions, or commands involving Kubernetes.

## **What are the benefits of using k8s?**

🚀 **Scalability:** Kubernetes allows easy scaling of applications, handling increased demand effortlessly.

🌐 **Portability:** Applications can run consistently across various environments, from on-premises to cloud.

🛡️ **Resilience:** Ensures high availability and reliability by managing and auto-restarting failed containers.

🎯 **Orchestration:** Simplifies deployment and management of complex applications through efficient orchestration.

🔧 **Resource Efficiency:** Optimizes resource utilization and facilitates better resource allocation.

📦 **Container Management:** Streamlines the handling of containers, making deployment and updates smoother.

## **What is Control Plane?**

The control plane in Kubernetes is like the brains of the operation! 🧠🌐 It manages and maintains the cluster's desired state, handling tasks like scheduling, scaling, and ensuring everything runs smoothly.

## **Difference between kubectl and kubelets**

**Kubectl -**

* A CLI tool for working with a Kubernetes cluster. It allows users to deploy and manage applications, inspect and manage cluster resources, and view logs.
    

**Kubelet -**

* A primary node agent that runs on each node in the Kubernetes cluster. It applies, creates, updates, and destroys containers on a Kubernetes node. Kubelet is a process that works on each node in the master and slave server of K8s architecture.