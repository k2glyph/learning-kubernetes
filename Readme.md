# Kubernetes
## What is Kubernetes?
Kubernetes is a orchestor for microservies app.<br />
Meaning of Orchestration => Arrangement, coordination and management of complex computer systems.<br />
## Kubernetes Archiecture 
![alt text](https://i.imgur.com/oo90cM6g.png)
### Kubernetes Master
* A Control Plane
* A collection of three process(kube-apiserver, kube-controller-manager, kube-scheduler)
#### kube-apiserver
* Validate and configure data for pods, services, replication controller and others.
* Provide frontend to cluster shared state
* Expose the API(REST) consume JSON via manifest files
* command `kube-apiserver [flags]`
#### kube-controller-manager
* controller of controller<br/>
    * Node controller
    * Endpoints controller
    * Namespace controller
    * ...
* Watches changes(Help maintain desired state)
* Is a control loop that watches shared state of the cluster through apiserver and make changes attempting to move the current state towards desired state.
* command `kube-controller-manager [flags]`

#### kube-scheduler
* watches apiserver for new pods
* Assign work to nodes
    * Affinity/ anti-affinity
    * constraints
    * resources
    * ...
* Is policy-rich, topoloygy-aware, workload specific function.
* Scheduler needs to take into<br />
    * Account individual and collective resource requirementh
* Workload-specific requirements will be exposed through the api as necessary.
* command `kube-scheduler`
#### Cluster Store
* Persistent storage
* Cluster state and config
* Uses etcd(etcd is a distributed key value store that provides reliable way to store data accross a cluster of machines NoSql database).
* Distributed, consistent watchable,
* The "source of truth" for the cluster

# Kuberctl command flow
![alt text](https://i.imgur.com/f8PsGWt.png)