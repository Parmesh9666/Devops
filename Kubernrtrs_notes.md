Diff b/t Docker and Kubernetes?
Docker is a containerization platform where as Kubernetes is a container orchestration platform

Containers are Ephemeral in nature. Ephemeral means short life. In kubernetes short life means containers can die or 
revive any time

1) Single host container.
On one host we have installed docker and running 100 containers. But due to some issue one container consumed high
CPU This will kill the another container.

2) Auto healing
If someone killed container immediately the application which is running inside container is not accessible. The devops 
engineer who start that killed container somebody has to act upon the container this process is called auto healing

3) Auto Scaling
Auto scaling means load getting increased in container1 then there are two ways to solve the problem in kuberntes
1. Manually increasing containers from 1 -10
2. Automatically
But Docker does not support these things

4) Minimalistic or simple platform
Simple platform means by default docker does not support any of your enterprise level application support.

Kubernetes will solve this all 4 problems
1. Single host container
2. Auto scaling
3. Auto healing
4. Enterprise level

How kubernetes solve this problems.
Kubernetes is by default cluster in nature --> maintained group of nodes
Single Host
In Kubernetes if container1 is impacting conatainer99 immediately Kubernetes will keep that container99 in different node.

Auto Scaling
Kubernetes has Replication controller --> If you are getting high load then In YAML file change replica set to 1-10
this is manual way to change YAML files. If we enable Horizontal Pod Auto Scalar(HPA) then it will increase pods 
automatically depends on the load.

Auto healing
Healing means Kubernetes controls. When a container goes down auto healing will get that and it will start new container.
In Kubernetes there will be API server this rollout new container when a container get damaged.

Enterprise level
In Kubernetes we use enterprise level container orchestration platform

=============================================================================

K8s Architecture

Kubernetes offering us to solve 4 different problems.
1. Cluster level
2. Auto healing
3. Auto scaling
4. Enterprise level

There are multiple components in Kubernetes.

<img width="392" height="235" alt="image" src="https://github.com/user-attachments/assets/e47a6089-9005-4d39-b536-af5afcce2bb4" />


When a user deploy pod into worker node we have a component in Kubernetes that is called as kubelet.
Here Kubelet is responsible for running a pod. Kubelet is ensuring that the pod is always running. 
In kubernetes we have pods has a container runtime.
In Kubernetes we have Kube-proxy and this kube-proxy basically provides networking. Every pod containing IP address and it has to providing load balancing capabilities.

There are mainly 3 components in data plane. They are
1. Kube-Proxy --> It is responsible for networking like generating IP address and load balancing 
2. Kubelet --> Responsible for creation of pods and it will ensure pods always in running state.
3. Container run time --> It is responsible for running container.

Master Node:
============

In Master node we have different components.
1. API server --> It will receive every request from external world
2. Scheduler --> It will take the decision to schedule the pods in node1 or node2...
3. ETCD --> It will store the all information of the cluster
4. Controller Manger --> It will ensure to managing inbuilt controllers
5. Cloud Controller Manger(CCM) --> 

==================================================================

How devops engineer manage 100's of clusters in production

Currently most using tool is **KOPS** 
KOPS means Kubernetes operations. KOPS is mainly managed by life cycle of Kubernetes such as Install, Upgradation, Modification and Deletion of cluster.

