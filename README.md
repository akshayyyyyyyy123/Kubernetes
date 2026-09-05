# Kubernetes Learning Roadmap

## 1. Kubernetes Fundamentals
- [ ] What is Kubernetes?
- [ ] Why Kubernetes?
- [ ] Kubernetes Architecture
- [ ] Control Plane
- [ ] Worker Nodes
- [ ] API Server
- [ ] etcd
- [ ] Scheduler
- [ ] Controller Manager
- [ ] Cloud Controller Manager
- [ ] Kubelet
- [ ] Kube-proxy
- [ ] Container Runtime
- [ ] Kubernetes API Objects
- [ ] Desired State vs Actual State
- [ ] Reconciliation Loop

---

## 2. Pods
- [ ] What is a Pod?
- [ ] Why Pods instead of containers?
- [ ] Pod Lifecycle
- [ ] Pod States
- [ ] Pod Restart Policies
- [ ] Multi-container Pods
- [ ] Init Containers
- [ ] Sidecar Containers
- [ ] Pod Networking
- [ ] Pod IP
- [ ] Pod YAML

---

## 3. Labels & Selectors
- [ ] Labels
- [ ] Label Selectors
- [ ] `matchLabels`
- [ ] `matchExpressions`
- [ ] Labels vs Selectors
- [ ] Practical Use Cases

---

## 4. Services & Networking Basics
- [ ] Why Services?
- [ ] Service Discovery
- [ ] ClusterIP
- [ ] NodePort
- [ ] LoadBalancer
- [ ] Service Selectors
- [ ] Service → Pod Communication
- [ ] Kubernetes DNS
- [ ] CoreDNS
- [ ] Service Endpoints / EndpointSlices

---

## 5. Controllers & Workloads
### ReplicationController
- [ ] ReplicationController
- [ ] Why ReplicationController?

### ReplicaSet
- [ ] ReplicaSet
- [ ] Desired Replicas
- [ ] ReplicaSet Selectors
- [ ] ReplicationController vs ReplicaSet

### Deployment
- [ ] Deployment
- [ ] Deployment → ReplicaSet → Pods
- [ ] Rolling Updates
- [ ] Recreate Strategy
- [ ] Rollout History
- [ ] Rollback
- [ ] Scaling
- [ ] Deployment Strategies

### Controllers
- [ ] Controller Pattern
- [ ] Reconciliation Loop
- [ ] Desired State
- [ ] Actual State

---

# 6. Kubernetes Scheduling

## Node Labels
- [x] Node Labels
- [x] Labeling Nodes
- [x] Viewing Node Labels

## nodeSelector
- [x] nodeSelector
- [x] Multiple nodeSelector Conditions
- [x] Limitations of nodeSelector

## Node Affinity
- [x] Node Affinity
- [x] Required Affinity
- [x] Preferred Affinity
- [x] `In`
- [x] `NotIn`
- [x] `Exists`
- [x] `DoesNotExist`
- [x] Affinity Weight
- [x] `IgnoredDuringExecution`

## Taints & Tolerations
- [x] Taints
- [x] Tolerations
- [x] `NoSchedule`
- [x] `PreferNoSchedule`
- [x] `NoExecute`
- [x] Taint Effects
- [x] Matching Tolerations
- [x] Taints vs Node Affinity
- [x] Dedicated Nodes
- [x] Combining Taints + Tolerations + Affinity

## Advanced Scheduling
- [ ] Pod Affinity
- [ ] Pod Anti-Affinity
- [ ] Topology Spread Constraints
- [ ] Scheduling Profiles
- [ ] Priority Classes
- [ ] Pod Priority
- [ ] Preemption
- [ ] Scheduler Filtering
- [ ] Scheduler Scoring
- [ ] Scheduler Framework

---

# 7. DaemonSet
- [ ] What is DaemonSet?
- [ ] Why DaemonSet?
- [ ] DaemonSet vs Deployment
- [ ] One Pod per Node
- [ ] DaemonSet Scheduling
- [ ] DaemonSet Updates
- [ ] DaemonSet Rollback
- [ ] DaemonSet + NodeSelector
- [ ] DaemonSet + Node Affinity
- [ ] DaemonSet + Tolerations
- [ ] Real-world DaemonSets
  - [ ] Log Collectors
  - [ ] Monitoring Agents
  - [ ] Security Agents
  - [ ] Datadog Agents
  - [ ] Fluent Bit

---

# 8. StatefulSet
- [ ] StatefulSet
- [ ] Stateless vs Stateful Applications
- [ ] Stable Pod Identity
- [ ] Stable Network Identity
- [ ] Ordered Deployment
- [ ] Ordered Scaling
- [ ] StatefulSet Updates
- [ ] Persistent Storage with StatefulSet
- [ ] Headless Services
- [ ] StatefulSet vs Deployment
- [ ] StatefulSet Limitations
- [ ] Real-world StatefulSet Examples

---

# 9. Kubernetes Storage
- [ ] Container Storage
- [ ] Volumes
- [ ] `emptyDir`
- [ ] `hostPath`
- [ ] Persistent Storage
- [ ] PersistentVolume (PV)
- [ ] PersistentVolumeClaim (PVC)
- [ ] StorageClass
- [ ] Static Provisioning
- [ ] Dynamic Provisioning
- [ ] Access Modes
- [ ] Reclaim Policies
- [ ] Volume Modes
- [ ] CSI
- [ ] CSI Drivers
- [ ] EBS CSI Driver
- [ ] EFS CSI Driver
- [ ] StatefulSet + PVC
- [ ] Storage in EKS

---

# 10. Jobs & CronJobs

## Job
- [ ] What is a Job?
- [ ] Job Completion
- [ ] Parallel Jobs
- [ ] `completions`
- [ ] `parallelism`
- [ ] `backoffLimit`
- [ ] Job Failure Handling
- [ ] Job Cleanup

## CronJob
- [ ] What is CronJob?
- [ ] Cron Expressions
- [ ] Scheduled Jobs
- [ ] Concurrency Policies
- [ ] Job History
- [ ] CronJob Failure Handling

---

# 11. ConfigMaps & Secrets
- [ ] ConfigMap
- [ ] Environment Variables
- [ ] ConfigMap as Volume
- [ ] Secrets
- [ ] Secret Types
- [ ] Secrets as Environment Variables
- [ ] Secrets as Volumes
- [ ] ConfigMap vs Secret
- [ ] Secret Security
- [ ] External Secrets
- [ ] AWS Secrets Manager Integration

---

# 12. Kubernetes Networking
- [ ] Kubernetes Network Model
- [ ] Pod-to-Pod Networking
- [ ] Pod-to-Service Networking
- [ ] Service-to-Service Communication
- [ ] Cluster Networking
- [ ] CNI
- [ ] CNI Plugins
- [ ] AWS VPC CNI
- [ ] CoreDNS
- [ ] Network Namespaces
- [ ] Ingress
- [ ] Ingress Controller
- [ ] Gateway API
- [ ] NetworkPolicy
- [ ] NetworkPolicy Selectors
- [ ] Ingress vs Service
- [ ] Network Troubleshooting

---

# 13. Kubernetes Security

## RBAC
- [ ] Authentication vs Authorization
- [ ] RBAC
- [ ] Role
- [ ] ClusterRole
- [ ] RoleBinding
- [ ] ClusterRoleBinding
- [ ] ServiceAccount
- [ ] User vs ServiceAccount
- [ ] Least Privilege
- [ ] RBAC Troubleshooting

## Pod Security
- [ ] SecurityContext
- [ ] Pod SecurityContext
- [ ] Container SecurityContext
- [ ] runAsUser
- [ ] runAsNonRoot
- [ ] Capabilities
- [ ] Privileged Containers
- [ ] Read-only Root Filesystem
- [ ] Pod Security Standards
- [ ] Pod Security Admission

---

# 14. Resource Management
- [ ] CPU Requests
- [ ] CPU Limits
- [ ] Memory Requests
- [ ] Memory Limits
- [ ] Requests vs Limits
- [ ] QoS Classes
  - [ ] Guaranteed
  - [ ] Burstable
  - [ ] BestEffort
- [ ] ResourceQuota
- [ ] LimitRange
- [ ] OOMKilled
- [ ] CPU Throttling

---

# 15. Health Checks & Probes
- [ ] Liveness Probe
- [ ] Readiness Probe
- [ ] Startup Probe
- [ ] HTTP Probe
- [ ] TCP Probe
- [ ] Exec Probe
- [ ] Probe Configuration
- [ ] Probe Failure Behavior
- [ ] Liveness vs Readiness
- [ ] Startup Probe Use Cases

---

# 16. Autoscaling

## HPA
- [ ] Horizontal Pod Autoscaler
- [ ] CPU-based Scaling
- [ ] Memory-based Scaling
- [ ] Custom Metrics
- [ ] HPA Algorithm
- [ ] HPA Configuration
- [ ] HPA Troubleshooting

## VPA
- [ ] Vertical Pod Autoscaler
- [ ] Request Recommendations
- [ ] VPA Modes

## Cluster Autoscaling
- [ ] Cluster Autoscaler
- [ ] Node Scaling
- [ ] Pending Pods and Node Scaling

## Karpenter
- [ ] What is Karpenter?
- [ ] Karpenter Architecture
- [ ] NodePools
- [ ] NodeClaims
- [ ] Karpenter vs Cluster Autoscaler
- [ ] Karpenter in EKS

---

# 17. Helm
- [ ] Why Helm?
- [ ] Helm Architecture
- [ ] Helm Charts
- [ ] Chart Structure
- [ ] `Chart.yaml`
- [ ] `values.yaml`
- [ ] Templates
- [ ] Template Functions
- [ ] Helm Install
- [ ] Helm Upgrade
- [ ] Helm Rollback
- [ ] Helm Release
- [ ] Helm Dependencies
- [ ] Helm Hooks
- [ ] Helm Best Practices

---

# 18. Kubernetes Observability
- [ ] Kubernetes Logs
- [ ] Kubernetes Events
- [ ] Metrics
- [ ] Container Metrics
- [ ] Node Metrics
- [ ] kube-state-metrics
- [ ] Metrics Server
- [ ] Prometheus
- [ ] Grafana
- [ ] Datadog
- [ ] Alerting
- [ ] Monitoring Control Plane
- [ ] Monitoring Worker Nodes
- [ ] Monitoring Applications

---

# 19. Kubernetes Troubleshooting
- [ ] Pod Pending
- [ ] CrashLoopBackOff
- [ ] ImagePullBackOff
- [ ] ErrImagePull
- [ ] OOMKilled
- [ ] CreateContainerConfigError
- [ ] ContainerCreating
- [ ] Node NotReady
- [ ] Service Not Working
- [ ] DNS Troubleshooting
- [ ] Networking Troubleshooting
- [ ] Storage Troubleshooting
- [ ] Scheduling Troubleshooting
- [ ] `kubectl describe`
- [ ] `kubectl logs`
- [ ] `kubectl exec`
- [ ] `kubectl get events`

---

# 20. Advanced Kubernetes Concepts
- [ ] Admission Controllers
- [ ] Mutating Admission Webhooks
- [ ] Validating Admission Webhooks
- [ ] CRDs
- [ ] Custom Resources
- [ ] Operators
- [ ] Operator Pattern
- [ ] Finalizers
- [ ] OwnerReferences
- [ ] Garbage Collection
- [ ] API Aggregation
- [ ] Kubernetes API Extensions
- [ ] Informers
- [ ] Watches
- [ ] Leader Election
- [ ] Controllers Internals

---

# 21. Kubernetes Internals
- [ ] API Server Request Flow
- [ ] Authentication
- [ ] Authorization
- [ ] Admission
- [ ] Object Persistence
- [ ] etcd Internals
- [ ] Scheduler Internals
- [ ] Controller Manager Internals
- [ ] Kubelet Internals
- [ ] Pod Creation Flow
- [ ] Pod Scheduling Flow
- [ ] Pod Termination Flow
- [ ] Deployment Update Flow
- [ ] Service Routing Flow
- [ ] EndpointSlice Controller
- [ ] Garbage Collector
- [ ] Kubernetes Reconciliation

---

# 22. GitOps
- [ ] What is GitOps?
- [ ] GitOps Principles
- [ ] Desired State
- [ ] Git as Source of Truth
- [ ] Argo CD
- [ ] Argo CD Architecture
- [ ] Application
- [ ] ApplicationSet
- [ ] Sync
- [ ] Auto Sync
- [ ] Drift Detection
- [ ] Rollback
- [ ] Multi-cluster GitOps
- [ ] Helm + Argo CD
- [ ] GitOps Best Practices

---

# 23. EKS — AWS Kubernetes

## EKS Architecture
- [ ] EKS Overview
- [ ] EKS Control Plane
- [ ] EKS Worker Nodes
- [ ] Managed Node Groups
- [ ] Self-managed Nodes
- [ ] Fargate
- [ ] EKS Networking

## EKS Networking
- [ ] VPC
- [ ] Subnets
- [ ] AWS VPC CNI
- [ ] ENIs
- [ ] Pod IP Allocation
- [ ] Security Groups
- [ ] Security Groups for Pods
- [ ] Load Balancers

## EKS Identity
- [ ] IAM Roles
- [ ] IRSA
- [ ] EKS Pod Identity
- [ ] IRSA vs Pod Identity
- [ ] ServiceAccounts + IAM

## EKS Storage
- [ ] EBS CSI
- [ ] EFS CSI
- [ ] StorageClasses
- [ ] Dynamic Provisioning

## EKS Load Balancing
- [ ] AWS Load Balancer Controller
- [ ] ALB
- [ ] NLB
- [ ] Ingress + ALB
- [ ] Service + NLB

## EKS Scaling
- [ ] HPA
- [ ] Cluster Autoscaler
- [ ] Karpenter
- [ ] Node Groups
- [ ] Spot Instances

---

# 24. Production Kubernetes
- [ ] High Availability
- [ ] Multi-AZ Architecture
- [ ] Cluster Upgrades
- [ ] Zero-Downtime Deployments
- [ ] Pod Disruption Budgets
- [ ] Disaster Recovery
- [ ] Backup & Restore
- [ ] etcd Backup
- [ ] Resource Optimization
- [ ] Cost Optimization
- [ ] Security Best Practices
- [ ] Observability
- [ ] Production Troubleshooting
- [ ] Capacity Planning
- [ ] Multi-cluster Architecture

---

# 25. Real-World Projects

## Project 1 — Basic Application
- [ ] Deployment
- [ ] Service
- [ ] ConfigMap
- [ ] Secret
- [ ] Probes
- [ ] Resource Requests/Limits

## Project 2 — Production Application
- [ ] Deployment
- [ ] HPA
- [ ] Ingress
- [ ] TLS
- [ ] ConfigMap
- [ ] Secrets
- [ ] Monitoring
- [ ] Logging

## Project 3 — Stateful Application
- [ ] StatefulSet
- [ ] Headless Service
- [ ] PVC
- [ ] StorageClass
- [ ] Persistent Storage

## Project 4 — Observability
- [ ] DaemonSet
- [ ] Log Collector
- [ ] Prometheus
- [ ] Grafana
- [ ] Alerts

## Project 5 — Production EKS
- [ ] EKS Cluster
- [ ] VPC
- [ ] Node Groups
- [ ] Karpenter
- [ ] AWS Load Balancer Controller
- [ ] EBS CSI
- [ ] Pod Identity
- [ ] HPA
- [ ] Monitoring
- [ ] Logging

## Project 6 — GitOps
- [ ] Git Repository
- [ ] Helm Chart
- [ ] Argo CD
- [ ] Automated Deployment
- [ ] Drift Detection
- [ ] Rollback

---

# 26. Interview Preparation
- [ ] Kubernetes Architecture Questions
- [ ] Pod Questions
- [ ] Deployment Questions
- [ ] ReplicaSet Questions
- [ ] Service Questions
- [ ] Scheduling Questions
- [ ] DaemonSet Questions
- [ ] StatefulSet Questions
- [ ] Storage Questions
- [ ] Networking Questions
- [ ] Security Questions
- [ ] RBAC Questions
- [ ] Autoscaling Questions
- [ ] Helm Questions
- [ ] Troubleshooting Questions
- [ ] EKS Questions
- [ ] Scenario-based Questions
- [ ] Production Architecture Questions
