## Kubernetes Components
- Pod
- Ip Address Assigned to pod and Service assigned to pod
- ConfigMap- Contains URLs of databases or other services, Connected to pod
- Secret- Used for storing things like passwords and usernames (You cannot store these in ConfigMap) (also connected to pod)
   - base64 Encoded
- Ingress- Ingress is a powerful tool for managing external access to your applications in a Kubernetes cluster and is commonly used when you want to expose your services to the internet or manage routing for different microservices within the cluster.
- Volumes- Attaches physical storage/cloud storage to pod for storing data (so its not lost)
- Deployment- Used to update, self-healing, create replicas of application (helps if a pod dies)
- Statefulset- Same as deployment but used for stateful apps or databases (this is compex so mostly databases are hosted outside K8s servers to avoid using this)
## Kubernetes Architecture 
- Cluster -> Node -> Pod -> Container -> Application + Dependencies
- Schedule new pod -> API Server -> Scheduler -> Where to put the Pod -> Kubelet -> Controller Manager
- Master Node- Think of this as the "brain" of Kubernetes. It manages and orchestrates the entire operation.
  
    1. **API Server**: The command center for Kubernetes. It receives and processes commands from users and communicates with the worker nodes.
    2. **Controller Manager**: Keeps an eye on the cluster's desired state, ensuring it matches the actual state. Think of it as the supervisor of your applications.
    3. **Scheduler**: This component acts as a traffic cop, deciding where to run your applications (called "pods") based on available resources.
    4. **etcd**: Think of etcd as the memory of Kubernetes. It stores critical configuration data and the current state of the cluster. (Actual application data is not stored here)
       
- Node contains multiple pods on it
- Every node run 3 services
   - Container Runtime- The container runtime is the "engine" that starts and manages containers on a node.
   - Kubelet- The Kubelet watches for pod specifications sent by the Kubernetes control plane (the master) and makes sure the pods are started, stopped, and maintained according to those specifications.
   - Kube Proxy- Role- Kube Proxy is like a "traffic cop" for network traffic within the cluster.
     
      - Key Functions-
        - Setting up and managing rules for network address translation (NAT) and load balancing.
        - Routing traffic to the appropriate pods and services.
        - Implementing network policies and security controls.
  
