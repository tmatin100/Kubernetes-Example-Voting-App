# Kubernetes-Example-Voting-App

The purpose of **Kubernetes** is to host your applications in the form of containers in an automated fashion so that you can easily 
deploy as many instances of your application as required, and easily enable communication between different services within your 
application. 

**Master Node**- responsible for the cluster managment, planing, scheduleing, and monitioring.         
**Worker Nodes**- Host applications as containers (inside Pods)

# ----------Master Node Componnets-----------
1. **Etcd Cluster** -information is stored in a highly availbe key value store. 
               ETCD is a distrubuted reliable-keyvalue store that is simple, secure, and fast. 

2. **Kube-Apiserver**- primariy managment component of kubernetes, responsible for orchestrating all operations within the cluster. It
                exposes the kubernetes api which enable external users to perform managmnet operations on the cluster as well as the 
                various controllers to monitor the state of the cluster and make necessary changes as requreid, and by the worker nodes 
                to communicate with the server. 

3. **Controller-Manager**- The kube conntroller manager manages various components in kubernetes. 
   A controller is a componnent in a master that has their own set of responsiblites, such as monitirong and remediating
   containers. 

4.  A **Controller** is a process that continously monitors the state of various components within the system 
    and works towards bringing the whole system to the desired functioning state.
  
      4.a. **Node-Controller**- takes care of nodes, responsible for onboarding new nodes to the cluster, handling situations where
                                nodes become unavailble or gets destroyed.
                    
      4.b. **Replicaiton-Controller**- Ensures that desired number of containers are running at all times in a replication group. 

5. **Kube-Scheduler** - identifies the right node and places containers based on the container's resource requriements, the worker 
                        node's capacity, or any other policies or contstarints such as taint or tolerations, or  node afinity rules that
                        are on them. 
                 
# ---------Worker Node Componnents-----------

6. **Container Runtime Engine** - Docker, cotainerd, Rkt etc. needs to be installed on all the nodes, since we use containers for everythig. 


7. **Kubelet**- an agent that runs on each node in a cluster, and listens for the instructions from the kube-apiserver, and deploys or destroys containers on the nodes as requried. The Kube-apiserver periodicly fetches status report from the kubelet, in order to monitor the status of the nodes and containers on them. 

8. **Kube-proxy** - service that ensures that necesary rules are in place on the worker nodes to allow the containers running on them
                   to reach eachoter. 
# ---------Client Componnents-----------
9. **Kubectl** - The kubectl command line tool lets you control Kubernetes clusters. For configuration, kubectl looks for a file named config in the **$HOME/.kube** directory. You can specify other kubeconfig files by setting the KUBECONFIG environment variable or by setting the --kubeconfig flag.

**Syntax
Use the following syntax to run kubectl commands from your terminal window:**

**kubectl [command] [TYPE] [NAME] [flags]**

**kubectl get pods pod1**

Refer to the document for more details: 
https://kubernetes.io/docs/reference/kubectl/overview/
