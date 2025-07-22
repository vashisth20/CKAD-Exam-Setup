# 🧪 CKAD Imperative Command Cheatsheet

These commands are fast for scoring quick wins. Use them when YAML isn’t required or use with `$dr` (`--dry-run=client`) to generate templates.

---

## 🔧 Core Commands

```bash
# Create a pod
kubectl run nginx --image=nginx

# Create a pod with dry-run
kubectl run nginx --image=nginx $dr > pod.yaml

# Create a deployment
kubectl create deployment web --image=nginx

# Create a deployment with 3 replicas
kubectl create deployment web --image=nginx --replicas=3

# Expose a pod as ClusterIP service
kubectl expose pod nginx --port=80 --target-port=80

# Expose a deployment as NodePort
kubectl expose deployment web --type=NodePort --port=80

# Scale a deployment
kubectl scale deployment web --replicas=5

# Delete a pod instantly
kubectl delete pod nginx $now
```

## 📦 ConfigMap & Secret Imperative Commands

```bash
# Create a ConfigMap from literal
kubectl create configmap app-config --from-literal=APP_COLOR=blue

# Create a Secret from literal
kubectl create secret generic db-secret --from-literal=username=admin --from-literal=password=pass123

# Generate a Secret YAML (dry-run)
kubectl create secret generic mysecret --from-literal=key=val $dr > secret.yaml
```

## 🛠️ Generate YAML with Dry Run

```bash
# Pod
k run nginx --image=nginx $dr > pod.yaml

# Deployment
k create deploy nginx --image=nginx $dr > deployment.yaml

# Service
k expose pod nginx --port=80 $dr > svc.yaml
```
