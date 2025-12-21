This repository provides a curated list of useful resources to learn concepts about Kubernetes and prepare for the CKA exam.

## **Exam Objectives**

The CNCF curriculum for the CKA can be found [here](https://github.com/cncf/curriculum/blob/master/CKA_Curriculum_v1.34.pdf).

The exam duration is 2 hours, and to pass the exam a minimum score of 66% is required. The certification is valid for 2 years.

The exam evaluates the following areas with an approximate weight per section (the links contain information about each topic):

1. [**Troubleshooting**](https://github.com/WahlNetwork/certified-kubernetes-administrator-cka-exam/blob/main/objectives/objective5.md) (30%)
2. [**Cluster Architecture, Installation & Configuration**](https://github.com/WahlNetwork/certified-kubernetes-administrator-cka-exam/blob/main/objectives/objective1.md) (25%)
3. [**Services & Networking**](https://github.com/WahlNetwork/certified-kubernetes-administrator-cka-exam/blob/main/objectives/objective3.md) (20%)
4. [**Workloads & Scheduling**](https://github.com/WahlNetwork/certified-kubernetes-administrator-cka-exam/blob/main/objectives/objective2.md) (15%)
5. [**Storage**](https://github.com/WahlNetwork/certified-kubernetes-administrator-cka-exam/blob/main/objectives/objective4.md) (10%)

---

## Set up a local K8S cluster

> **Info**  
> Before getting started with Kubernetes, it is necessary to have a local environment to test and deploy configurations.

I personally recommend using virtualization tools such as [VirtualBox](https://www.virtualbox.org/) together with infrastructure-as-code tools like [Vagrant](https://developer.hashicorp.com/vagrant) to set up a cluster in an automated way. In the Open Source community there are projects that provide this functionality. My personal recommendations are:

- [Vagrantfile and Scripts to Automate Kubernetes Setup using Kubeadm](https://github.com/techiescamp/vagrant-kubeadm-kubernetes)
- [Deploy a Production Ready Kubernetes Cluster](https://github.com/kubernetes-sigs/kubespray)

---

## 📚 Theory and useful links

### General Kubernetes concepts

- [Kubernetes Overview](https://kubernetes.io/docs/concepts/overview/)
  - [Kubernetes! The Basics](https://medium.com/@h.stoychev87/kubernetes-the-basics-ccadefb48037)
- [Kubernetes Architecture](https://devopscube.com/kubernetes-architecture-explained/)
  - [Kubernetes Cluster Architecture, Installation, and Configuration](https://medium.com/@h.stoychev87/kubernetes-cluster-architecture-installation-and-configuration-77b9306db158)
- [Kubeconfig File Explained](https://devopscube.com/kubernetes-kubeconfig-file/)
- [Understand Kubernetes Objects And Resources](https://devopscube.com/kubernetes-objects-resources/)
- [Kubernetes Tutorials](https://www.youtube.com/playlist?list=PLiMWaCMwGJXnHmccp2xlBENZ1xr4FpjXF) by Anton Putra (Video)
- [Kubernetes Zero to Hero: The Complete Beginner’s Guide (2025 Edition)](https://youtu.be/MTHGoGUFpvE) by Alta3 Research (Video)

### Concepts about Pods and Pod-dependent objects

All essential Kubernetes concepts revolve around the Pod. Understanding how Pods work is fundamental, as many objects are built around them.

- [Kubernetes Pod Guide](https://devopscube.com/kubernetes-pod/)
- [Kubernetes Pod Lifecycle](https://devopscube.com/kubernetes-pod-lifecycle/)
- [Kubernetes Pods Troubleshooting](https://devopscube.com/troubleshoot-kubernetes-pods/)
- [Sidecar Containers](https://kubernetes.io/docs/concepts/workloads/pods/sidecar-containers/)
  - [Kubernetes Sidecar Containers: Use Cases and Best Practices](https://www.groundcover.com/blog/kubernetes-sidecar)
  - [The Power of Sidecar Containers in Kubernetes Explained](https://last9.io/blog/sidecar-containers-in-kubernetes/)
- [What is a Kubernetes ReplicaSet?](https://www.sysdig.com/learn-cloud-native/kubernetes-replicasets-overview)
- [What Is a Kubernetes Deployment?](https://www.sysdig.com/learn-cloud-native/kubernetes-replicasets-overview)
  - [Understand Deployments And How To Perform Rolling Update And Rollbacks](https://github.com/WahlNetwork/certified-kubernetes-administrator-cka-exam/blob/main/objectives/objective2.md#21-understand-deployments-and-how-to-perform-rolling-update-and-rollbacks)
- [Kubernetes StatefulSet](https://website.vcluster.com/blog/kubernetes-statefulset-examples-and-best-practices)
  - [Kubernetes Deployment vs. StatefulSets](https://www.baeldung.com/ops/kubernetes-deployment-vs-statefulsets) 
- [Kubernetes DaemonSet](https://devopscube.com/kubernetes-daemonset/)
- [Kubernetes Jobs and CronJobs](https://devopscube.com/create-kubernetes-jobs-cron-jobs/)

### Concepts about Services and Ingress

Applications running in Pods may need to be accessible both from inside the cluster and from outside the cluster.

**Services** provide a stable IP and DNS name, allowing Pods to communicate with each other and receive traffic transparently, even when Pods are created, deleted, or replaced.

- [Kubernetes Services simply visually explained](https://medium.com/swlh/kubernetes-services-simply-visually-explained-2d84e58d70e5) (requires a Medium account)
- [Understand ClusterIP, NodePort, LoadBalancer Service Types And Endpoints](https://github.com/WahlNetwork/certified-kubernetes-administrator-cka-exam/blob/main/objectives/objective3.md#33-understand-clusterip-nodeport-loadbalancer-service-types-and-endpoints)

In addition, applications running on Kubernetes may require more than a single access point. Using an **Ingress** object, you can define rules that specify how traffic is routed. For example:
- `www.example.com/shop` → *shop* service
- `www.example.com/blog` → *blog* service

Ingress acts as a kind of gateway that manages incoming traffic to multiple Kubernetes backend services.

- [Kubernetes Ingress Tutorial](https://devopscube.com/kubernetes-ingress-tutorial/)
- [Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/)
  - [Ingress-NGINX Controller End-of-Life: 2026. Alternatives and Architecture](https://medium.com/@h.stoychev87/nginx-ingress-end-of-life-2026-f30e53e14a2e)
- [Ingress Controllers](https://kubernetes.io/docs/concepts/services-networking/ingress-controllers/)

### Concepts about Network & Network Policies

- [Kubernetes Networking: A Deep Dive](https://medium.com/@h.stoychev87/kubernetes-networking-a-deep-dive-6081d794e97c)
- [Kubernetes Network Policy](https://kubernetes.io/docs/concepts/services-networking/network-policies/)
- [Network Policy Editor](https://editor.networkpolicy.io/)
- [Network Policy Recipes](https://github.com/ahmetb/kubernetes-network-policy-recipes)

### Concepts about Logging & Monitoring

- [Kubernetes Logging: A Comprehensive Guide For Beginners](https://devopscube.com/kubernetes-logging-tutorial/)

---

## ⚙️ Practice

- [GitHub: CKA-PREP](https://github.com/CameronMetcalfe22/CKA-PREP?tab=readme-ov-file)
- [GitHub: CKA Exercises](https://github.com/chadmcrowell/CKA-Exercises)
- [Kubernetes Hands-On Projects for Learning](https://github.com/techiescamp/kubernetes-projects)
- [Killer Shell CKA](https://killercoda.com/killer-shell-cka)
