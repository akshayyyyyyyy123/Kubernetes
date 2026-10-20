## Understanding your HPA output

```
# kubectl get pods -l app=php-apache -w
NAME                         READY   STATUS    RESTARTS      AGE
php-apache-8cdd76588-kqdwk   1/1     Running   1 (14h ago)   14h
php-apache-8cdd76588-7ggbt   0/1     Pending   0             0s
php-apache-8cdd76588-7ggbt   0/1     Pending   0             0s
php-apache-8cdd76588-vldgc   0/1     Pending   0             0s
php-apache-8cdd76588-lpqcn   0/1     Pending   0             0s
php-apache-8cdd76588-vldgc   0/1     Pending   0             0s
php-apache-8cdd76588-lpqcn   0/1     Pending   0             0s
php-apache-8cdd76588-7ggbt   0/1     ContainerCreating   0             0s
php-apache-8cdd76588-vldgc   0/1     ContainerCreating   0             0s
php-apache-8cdd76588-lpqcn   0/1     ContainerCreating   0             0s
php-apache-8cdd76588-lpqcn   1/1     Running             0             1s
php-apache-8cdd76588-7ggbt   1/1     Running             0             2s
php-apache-8cdd76588-vldgc   1/1     Running             0             3s
php-apache-8cdd76588-fmn94   0/1     Pending             0             0s
php-apache-8cdd76588-fmn94   0/1     Pending             0             0s
php-apache-8cdd76588-fmn94   0/1     ContainerCreating   0             0s
php-apache-8cdd76588-fmn94   1/1     Running             0             3s
```

```
# kubectl get hpa php-apache --watch
NAME         REFERENCE               TARGETS       MINPODS   MAXPODS   REPLICAS   AGE
php-apache   Deployment/php-apache   cpu: 0%/50%   1         5         1          14h
php-apache   Deployment/php-apache   cpu: 1%/50%   1         5         1          15h
php-apache   Deployment/php-apache   cpu: 250%/50%   1         5         1          15h
php-apache   Deployment/php-apache   cpu: 250%/50%   1         5         4          15h
php-apache   Deployment/php-apache   cpu: 250%/50%   1         5         5          15h
php-apache   Deployment/php-apache   cpu: 112%/50%   1         5         5          15h
php-apache   Deployment/php-apache   cpu: 83%/50%    1         5         5          15h
php-apache   Deployment/php-apache   cpu: 84%/50%    1         5         5          15h
php-apache   Deployment/php-apache   cpu: 84%/50%    1         5         5          15h
php-apache   Deployment/php-apache   cpu: 84%/50%    1         5         5          15h
php-apache   Deployment/php-apache   cpu: 52%/50%    1         5         5          15h
php-apache   Deployment/php-apache   cpu: 0%/50%     1         5         5          15h
```

<img width="852" height="421" alt="Screenshot 2026-10-20 at 5 21 06 PM" src="https://github.com/user-attachments/assets/08040376-852c-429a-988f-91e326035b0c" />


The actual output shows these stages:

<img width="661" height="278" alt="Screenshot 2026-10-20 at 5 25 51 PM" src="https://github.com/user-attachments/assets/156042f7-8c55-4856-8d01-5c30f0efd21e" />

Important: CPU utilization is measured against the CPU request, not the CPU limit. Your container requests 200m CPU, so a reported 250% means average CPU usage 
was approximately \(200m \times 2.5 = 500m\) per Pod.

---

## How Kubernetes scaled your application

<img width="795" height="546" alt="Screenshot 2026-10-20 at 5 28 53 PM" src="https://github.com/user-attachments/assets/7a18bc74-eded-4cb1-a040-4d5b1ccb6bf1" />

Notice something important: the HPA doesn't create Pods directly. It updates the desired replica count of your Deployment. The Deployment's ReplicaSet then creates 
or removes Pods to reach that count. Your HPA reached 5 replicas, which is your configured maximum. It didn't create a sixth Pod because maxReplicas: 5 prevents that.

---

## Why did CPU drop to 0% while replicas stayed at 5?

- When the load generator stopped sending requests, CPU usage dropped. But HPA doesn't necessarily remove Pods immediately.

- Kubernetes uses a stabilization period and scaling policies to avoid rapidly creating and deleting Pods whenever CPU fluctuates. The default scale-down stabilization window is typically 5 minutes.

- Also, your minReplicas is 1, so once the load has subsided and the scale-down rules permit it, HPA can reduce the replicas toward one.

---

### One final takeaway: you've now observed the complete HPA cycle — low load, high CPU, scale-up, load reduction, and eventual scale-down. That's the fundamental behavior you need to understand before moving to more advanced autoscaling topics.
