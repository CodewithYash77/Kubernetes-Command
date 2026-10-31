# ☸️ Kubernetes (K8s) Commands Cheat Sheet

A simple Kubernetes command guide for Beginners and DevOps Engineers.

Learn Kubernetes commands with easy explanations and practical examples.

## 📌 What is Kubernetes?

Kubernetes is an open-source platform used to manage containerized applications.

It helps to:

* Deploy applications.
* Manage containers.
* Scale applications.
* Restart failed containers.
* Manage application networking.

## 1. Basic Kubernetes Commands

| Command                          | Use                           |
| -------------------------------- | ----------------------------- |
| `kubectl version`                | Check Kubernetes version      |
| `kubectl cluster-info`           | Show cluster information      |
| `kubectl get nodes`              | Show all nodes                |
| `kubectl get namespaces`         | Show all namespaces           |
| `kubectl config view`            | Show Kubernetes configuration |
| `kubectl config current-context` | Show current cluster context  |
| `kubectl explain pod`            | Show Pod documentation        |
| `kubectl help`                   | Show help                     |

## 2. Pod Commands

A Pod is the smallest deployable unit in Kubernetes. It contains one or more containers.

| Command                                         | Use                           |
| ----------------------------------------------- | ----------------------------- |
| `kubectl get pods`                              | Show all Pods                 |
| `kubectl get pods -A`                           | Show Pods in all namespaces   |
| `kubectl get pods -o wide`                      | Show detailed Pod information |
| `kubectl describe pod POD_NAME`                 | Show Pod details              |
| `kubectl create deployment nginx --image=nginx` | Create a Deployment           |
| `kubectl delete pod POD_NAME`                   | Delete a Pod                  |
| `kubectl logs POD_NAME`                         | Show Pod logs                 |
| `kubectl exec -it POD_NAME -- sh`               | Enter Pod terminal            |
| `kubectl get pods --watch`                      | Watch Pod status              |

## 3. Deployment Commands

Deployment manages application Pods and maintains the desired number of replicas.

| Command                                         | Use                     |
| ----------------------------------------------- | ----------------------- |
| `kubectl get deployments`                       | Show Deployments        |
| `kubectl create deployment nginx --image=nginx` | Create Deployment       |
| `kubectl describe deployment nginx`             | Show Deployment details |
| `kubectl scale deployment nginx --replicas=3`   | Create 3 replicas       |
| `kubectl rollout status deployment/nginx`       | Check deployment status |
| `kubectl rollout history deployment/nginx`      | Show deployment history |
| `kubectl rollout undo deployment/nginx`         | Roll back deployment    |
| `kubectl delete deployment nginx`               | Delete Deployment       |

## 4. Service Commands

Service allows communication with applications running inside Pods.

| Command                                                      | Use                     |
| ------------------------------------------------------------ | ----------------------- |
| `kubectl get services`                                       | Show Services           |
| `kubectl describe service SERVICE_NAME`                      | Show Service details    |
| `kubectl expose deployment nginx --port=80 --type=NodePort`  | Expose Deployment       |
| `kubectl expose deployment nginx --port=80 --type=ClusterIP` | Create internal Service |
| `kubectl delete service SERVICE_NAME`                        | Delete Service          |

## 5. Namespace Commands

Namespaces help organize resources inside a Kubernetes cluster.

| Command                          | Use                             |
| -------------------------------- | ------------------------------- |
| `kubectl get namespaces`         | Show namespaces                 |
| `kubectl create namespace dev`   | Create namespace                |
| `kubectl describe namespace dev` | Show namespace details          |
| `kubectl delete namespace dev`   | Delete namespace                |
| `kubectl get pods -n dev`        | Show Pods in dev namespace      |
| `kubectl get all -n dev`         | Show resources in dev namespace |

## 6. ConfigMap Commands

ConfigMap stores application configuration data.

| Command                                                          | Use                    |
| ---------------------------------------------------------------- | ---------------------- |
| `kubectl get configmaps`                                         | Show ConfigMaps        |
| `kubectl create configmap app-config --from-literal=APP_ENV=dev` | Create ConfigMap       |
| `kubectl describe configmap app-config`                          | Show ConfigMap details |
| `kubectl delete configmap app-config`                            | Delete ConfigMap       |

## 7. Secret Commands

Secrets store sensitive information like passwords and tokens.

| Command                                                                    | Use                 |
| -------------------------------------------------------------------------- | ------------------- |
| `kubectl get secrets`                                                      | Show Secrets        |
| `kubectl create secret generic db-secret --from-literal=password=admin123` | Create Secret       |
| `kubectl describe secret db-secret`                                        | Show Secret details |
| `kubectl delete secret db-secret`                                          | Delete Secret       |

Note: Kubernetes Secret values are not automatically encrypted in every cluster configuration. Use proper access controls and encryption at rest.

## 8. Node Commands

Nodes are machines where Kubernetes runs application Pods.

| Command                           | Use                            |
| --------------------------------- | ------------------------------ |
| `kubectl get nodes`               | Show all nodes                 |
| `kubectl describe node NODE_NAME` | Show node details              |
| `kubectl cordon NODE_NAME`        | Stop scheduling new Pods       |
| `kubectl uncordon NODE_NAME`      | Allow scheduling Pods again    |
| `kubectl drain NODE_NAME`         | Safely evict eligible Pods     |
| `kubectl top nodes`               | Show node CPU and memory usage |

## 9. YAML File Commands

Kubernetes uses YAML files to define resources.

| Command                       | Use                           |
| ----------------------------- | ----------------------------- |
| `kubectl apply -f pod.yaml`   | Create or update resources    |
| `kubectl create -f pod.yaml`  | Create resources              |
| `kubectl delete -f pod.yaml`  | Delete resources              |
| `kubectl get -f pod.yaml`     | Show resources                |
| `kubectl diff -f pod.yaml`    | Preview configuration changes |
| `kubectl replace -f pod.yaml` | Replace an existing resource  |

## 10. Useful Troubleshooting Commands

| Command                            | Use                           |
| ---------------------------------- | ----------------------------- |
| `kubectl get pods`                 | Check Pod status              |
| `kubectl describe pod POD_NAME`    | Find Pod errors and events    |
| `kubectl logs POD_NAME`            | Check application logs        |
| `kubectl logs POD_NAME --previous` | Check previous container logs |
| `kubectl get events`               | Show cluster events           |
| `kubectl top pods`                 | Show Pod CPU and memory usage |
| `kubectl get pods -o wide`         | Check Pod IP and node         |
| `kubectl exec -it POD_NAME -- sh`  | Enter container shell         |

## 11. Labels and Selectors

Labels help organize and identify Kubernetes resources.

| Command                                | Use                     |
| -------------------------------------- | ----------------------- |
| `kubectl get pods --show-labels`       | Show Pod labels         |
| `kubectl label pod POD_NAME app=nginx` | Add a label             |
| `kubectl get pods -l app=nginx`        | Find Pods using a label |
| `kubectl label pod POD_NAME app-`      | Remove a label          |

## 12. Rollout Commands

Rollouts help manage application updates.

| Command                                    | Use                 |
| ------------------------------------------ | ------------------- |
| `kubectl rollout status deployment/nginx`  | Check update status |
| `kubectl rollout history deployment/nginx` | Show update history |
| `kubectl rollout undo deployment/nginx`    | Undo latest update  |
| `kubectl rollout restart deployment/nginx` | Restart Deployment  |

## 13. Scaling Commands

Scaling increases or decreases application replicas.

```bash
kubectl scale deployment nginx --replicas=3
```

Check replicas:

```bash
kubectl get deployments
```

Scale down:

```bash
kubectl scale deployment nginx --replicas=1
```

## 14. Complete Kubernetes Practical

### Step 1: Create Deployment

```bash
kubectl create deployment nginx --image=nginx
```

### Step 2: Check Pods

```bash
kubectl get pods
```

### Step 3: Create 3 Replicas

```bash
kubectl scale deployment nginx --replicas=3
```

### Step 4: Check Deployment

```bash
kubectl get deployments
```

### Step 5: Create NodePort Service

```bash
kubectl expose deployment nginx --type=NodePort --port=80
```

### Step 6: Check Services

```bash
kubectl get services
```

### Step 7: Check Pod Details

```bash
kubectl describe pods
```

### Step 8: Delete Deployment

```bash
kubectl delete deployment nginx
```

### Step 9: Delete Service

```bash
kubectl delete service nginx
```

## 15. Important Kubernetes Concepts

| Concept    | Meaning                             |
| ---------- | ----------------------------------- |
| Cluster    | Group of Kubernetes machines        |
| Node       | Machine that runs applications      |
| Pod        | Smallest deployable unit            |
| Container  | Application runtime environment     |
| Deployment | Manages Pods and replicas           |
| Service    | Provides network access to Pods     |
| Namespace  | Organizes cluster resources         |
| ConfigMap  | Stores configuration data           |
| Secret     | Stores sensitive configuration data |
| ReplicaSet | Maintains desired Pod replicas      |
| Volume     | Provides storage to Pods            |
| Ingress    | Manages HTTP/HTTPS external access  |

---

## 👨‍💻 Author

**Yash Pawar**

Cloud & DevOps | AWS | Linux | Docker | Kubernetes

* GitHub: https://github.com/CodewithYash77
* LinkedIn: https://linkedin.com/in/yashpawar11092005

⭐ If this guide helps you, give this repository a Star!

**Keep Learning | Keep Practicing | Keep Building 🚀**
