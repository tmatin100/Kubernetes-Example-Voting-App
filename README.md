# Kubernetes-Example-Voting-App

The purpose of Kubernetes is to host your applications in the form of containers in an automated fashion so that you can easily 
deploy as many instances of your application as required, and easily enable communication between diffent services within your 
application. 

Master Node- responsible for the cluster managment, planing, scheduleing, and monitioring.         
Worker Nodes- Host applications as containers (inside Pods)

----Master Node componnets------------------------------------------------------------------------------------------------------

1. Etcd Cluster -information is stored in a highly availbe key value store. 
               ETCD is a distrubuted reliable-keyvalue store that is Simple, secure, and fast. 

2. Kube-Apiserver- primariy managment component of kubernetes, responsible for orchestraging all operations within the cluster. It
                exposes the kubernetes api which enable external users to perform managmnet operations the cluster as well as the 
                various controllers to  monitor the state of the cluster and make necessary changes as requreid, and by the worker noeds 
                to communicate with the server. 

3. Controller-Manager- The kube conntroller manager manages various components in kubernetes. 
   A controller is a department or office in a master ship that has their own set of responsiblites, such as monitirong and remediating
   containers. 

5. A Controller is a process that continously monitors the state of various components within the system 
   and works towards bringing the whole system the desired functioning state.
  -Node-Controller- takes are of nodes, responsible for onboarding new nodes to the cluster, handling situations where
                   nodes become unavailble or gets destroyed. 
  -Replicaiton-Controller- Ensures that desired number of containers are running at all times in a replication group. 


6. Kube-Scheduler - identifies the right node and places containers based on the containers resource requriements, the worker 
                 node's capacity, or any other policies or contstarints such as taint or tolerations, or  node afinity rules that
                 are on them. 



----Worker Node Componnents--------------------------------------------------------------------------------------------------------

7. Container Runtime Engine- Docker, cotainerd, Rkt etc. needs to be installed on all the nodes, since we use containers for everythig. 


8. Kubelet(captin)- an agent that runs on each node in a cluster, and listens for the instructions from the kube-apiserver, an        
                 deploys or destroys containers on the nodes as requried. The Kube-apiserver eriodicly fetches status 
                 report from the kubelet, inorder to monitor the status of the nodes and containers on them. 

9. Kube-proxy - service that ensures that necesary rules are in place on the worker nodes to allow the containers running on them
             to reach eachoter. 


