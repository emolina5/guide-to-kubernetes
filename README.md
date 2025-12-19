# guide-to-kubernetes

**Objetivos examen:**
---------------------

El curriculum de la CNCF para el CKA se puede encontrar [aquí](https://github.com/cncf/curriculum/blob/master/CKA_Curriculum_v1.34.pdf).

El examen tiene una duración de 2 horas y para aprobar el examen se debe alcanzar una puntuación mínima del 66%. Tiene una validez de 2 años.

El examen evalúa los siguientes puntos con un peso aproximado por sección (en los enlaces se encuentra información sobre cada apartado):

1.  [**Troubleshooting**](https://github.com/WahlNetwork/certified-kubernetes-administrator-cka-exam/blob/main/objectives/objective5.md) (30%)
    
2.  [**Cluster Architecture, Installation & Configuration**](https://github.com/WahlNetwork/certified-kubernetes-administrator-cka-exam/blob/main/objectives/objective1.md) (25%)
    
3.  [**Services & Networking**](https://github.com/WahlNetwork/certified-kubernetes-administrator-cka-exam/blob/main/objectives/objective3.md) (20%)
    
4.  [**Workloads & Scheduling**](https://github.com/WahlNetwork/certified-kubernetes-administrator-cka-exam/blob/main/objectives/objective2.md) (15%)
    
5.  [**Storage**](https://github.com/WahlNetwork/certified-kubernetes-administrator-cka-exam/blob/main/objectives/objective4.md) (10%)
    

* * *

Configurar un cluster de K8S en local
-------------------------------------

Antes de comenzar con Kubernetes, es necesario contar con un entorno local para probar y desplegar configuraciones.

Personalmente recomiendo usar herramientas de virtualización como [VirtualBox](https://www.virtualbox.org/) junto con herramientas de definición de infraestructura como código, como [Vagrant](https://developer.hashicorp.com/vagrant), para configurar un clúster de forma automatizada. En la comunidad OpenSource existen proyectos que ofrecen esta funcionalidad. Mi recomendación personal es:

*   [vagrant-kubeadm-kubernetes](https://github.com/techiescamp/vagrant-kubeadm-kubernetes) (compatible con Windows, Linux y macOS intel)
    
*   [vagrant-kubeadm-mac-silicon](https://github.com/techiescamp/vagrant-kubeadm-mac-silicon) (optimizado para sistemas macOS con arquitectura arm64)
    

* * *

📚Teoría y enlaces de interés
-----------------------------

### Conceptos generales de Kubernetes

*   [Kubernetes Overview](https://kubernetes.io/docs/concepts/overview/)
    
    *   [Kubernetes! The Basics](https://medium.com/@h.stoychev87/kubernetes-the-basics-ccadefb48037) MUST READ!Green
        
*   [Kubernetes Architecture](https://devopscube.com/kubernetes-architecture-explained/)
    
    *   [Kubernetes Cluster Architecture, Installation, and Configuration](https://medium.com/@h.stoychev87/kubernetes-cluster-architecture-installation-and-configuration-77b9306db158)
        
*   [Kubeconfig File Explained](https://devopscube.com/kubernetes-kubeconfig-file/)
    
*   [Understand Kubernetes Objects And Resources](https://devopscube.com/kubernetes-objects-resources/)
    

### Conceptos sobre Pods y objetos dependiente de Pods

Todos los conceptos esenciales de Kubernetes giran en torno al Pod. Entender el funcionamiento de estos es fundamental ya que muchos objetos se construyen alrededor de él. A continuación, están adjuntadas guías de la comunidad que profundizan en distintos aspectos de los Pod.

*   [Kubernetes Pod Guide](https://devopscube.com/kubernetes-pod/)
    
*   [Kubernetes Pod Lifecycle](https://devopscube.com/kubernetes-pod-lifecycle/)
    
*   [Kubernetes Pods Troubleshooting](https://devopscube.com/troubleshoot-kubernetes-pods/)
    
*   [Sidecar Containers](https://kubernetes.io/docs/concepts/workloads/pods/sidecar-containers/)
    
    *   [Kubernetes Sidecar Containers: Use Cases and Best Practices](https://www.groundcover.com/blog/kubernetes-sidecar)
        
    *   [The Power of Sidecar Containers in Kubernetes Explained](https://last9.io/blog/sidecar-containers-in-kubernetes/)
        
*   [What is a Kubernetes ReplicaSet?](https://www.sysdig.com/learn-cloud-native/kubernetes-replicasets-overview)
    
*   [What Is a Kubernetes Deployment?](https://www.sysdig.com/learn-cloud-native/kubernetes-replicasets-overview)
    
    *   [Understand Deployments And How To Perform Rolling Update And Rollbacks](https://github.com/WahlNetwork/certified-kubernetes-administrator-cka-exam/blob/main/objectives/objective2.md#21-understand-deployments-and-how-to-perform-rolling-update-and-rollbacks)
        
*   [Kubernetes StatefulSet](https://website.vcluster.com/blog/kubernetes-statefulset-examples-and-best-practices)
    
*   [Kubernetes Daemonset](https://devopscube.com/kubernetes-daemonset/)
    
*   [Kubernetes Jobs and Cronjobs](https://devopscube.com/create-kubernetes-jobs-cron-jobs/)
    

### Conceptos sobre Services e Ingress

Las aplicaciones que se ejecutan en Pods pueden necesitar ser accesibles tanto desde dentro del clúster por otros servicios como desde fuera del clúster.

Los **Services** ofrecen una IP estable y un nombre DNS, lo que permite que los Pods se comuniquen entre sí y reciban tráfico de forma transparente, incluso cuando se crean, eliminan o reemplazan Pods. Así, el acceso a las aplicaciones se mantiene estable y no se ve afectado por estos cambios.

*   [Kubernetes Services simply visually explained](https://medium.com/swlh/kubernetes-services-simply-visually-explained-2d84e58d70e5) (requiere de cuenta en Medium para leer)
    
*   [Understand ClusterIP, NodePort, LoadBalancer Service Types And Endpoints](https://github.com/WahlNetwork/certified-kubernetes-administrator-cka-exam/blob/main/objectives/objective3.md#33-understand-clusterip-nodeport-loadbalancer-service-types-and-endpoints)
    

Además, las aplicaciones que se ejecutan en Kubernetes pueden requerir más que un único punto de acceso. Usando un objeto **Ingress** puedes definir reglas que indican cómo enrutarse el tráfico. Puedes configurar que el tráfico de `www.example.com/shop` se dirija al servicio shop y el de `www.example.com/blog` al servicio blog.  
Ingress actúa como una especie de gateway que gestiona el tráfico entrante hacia varios servicios backend de Kubernetes.

*   [Kubernetes Ingress Tutorial](https://devopscube.com/kubernetes-ingress-tutorial/)
    
*   [Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/)
    
    *   [Ingress-NGINX Controller End-of-Life: 2026. Alternatives and Architecture](https://medium.com/@h.stoychev87/nginx-ingress-end-of-life-2026-f30e53e14a2e)
        
*   [Ingress Controllers](https://kubernetes.io/docs/concepts/services-networking/ingress-controllers/)
    

### Conceptos sobre Network & Network Policies

*   [Kubernetes Networking: A Deep Dive](https://medium.com/@h.stoychev87/kubernetes-networking-a-deep-dive-6081d794e97c)
    
*   [Kubernetes Network Policy](https://kubernetes.io/docs/concepts/services-networking/network-policies/)
    
*   [Network Policy Editor](https://editor.networkpolicy.io/)
    
*   [Network Policy Recipes](https://github.com/ahmetb/kubernetes-network-policy-recipes)
    

### Conceptos sobre Logging & Monitoring

*   [Kubernetes Logging: A Comprehensive Guide For Beginners](https://devopscube.com/kubernetes-logging-tutorial/)
    

⚙️ Practice
-----------

*   [GitHub: CKA-PREP](https://github.com/CameronMetcalfe22/CKA-PREP?tab=readme-ov-file)
    
*   [GitHub: CKA Exercises](https://github.com/chadmcrowell/CKA-Exercises)
    
*   [Kubernetes Hands-On Projects for Learning](https://github.com/techiescamp/kubernetes-projects)
    
*   [Killer Shell CKA](https://killercoda.com/killer-shell-cka)