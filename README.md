# K&S
Kubernetes Control Node Architecture
This diagram illustrates the architecture and communication flow of a customized Kubernetes Control Node. It highlights the central role of the kube-apiserver and its interactions with standard Kubernetes control plane elements, the container runtime, and third-party infrastructure integrations.

Core Control Plane Components:

kube-apiserver (api): The central hub and front end for the Kubernetes control plane. All internal and external components route their communications through it.

etcd: A highly-available, distributed key-value store acting as the primary backing store for all cluster data and state.

kube-scheduler (sched): Responsible for watching newly created Pods that have no assigned node and selecting a node for them to run on.

kube-controller-manager (c-m): Runs the core controller processes that monitor and regulate the state of the cluster.

kubelet: The primary node agent that registers the node with the API server and ensures that containers are running within Pods.

Container Runtime:

containerd: The industry-standard core container runtime used by the kubelet to manage container lifecycles on the node.

Networking, Security & Service Mesh:

Cilium (cilium-agent / cilium-operator): Acts as the Container Network Interface (CNI). It uses eBPF to provide advanced networking, load balancing, and security policies.

Istio (istiod): The core control plane daemon for the Istio service mesh, responsible for service discovery, configuration, and certificate management.

High Availability & Load Balancing:

Kube-VIP: Provides a highly available (HA) virtual IP address and load balancing capabilities specifically for the control plane/API server.
