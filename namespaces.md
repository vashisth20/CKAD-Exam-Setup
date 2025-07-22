# 🗂️ CKAD Namespace & Context Management

Namespaces and contexts are key in CKAD. Switch them quickly to stay on track.

## 🧭 Context Switching

```bash
# List all contexts
kubectl config get-contexts
kc

# Use a specific context
kubectl config use-context <context-name>
```

## 📁 Manage Namespaces

```bash
# View all namespaces
kubectl get ns

# Create a namespace
kubectl create namespace dev

# Set the current namespace
kubectl config set-context --current --namespace=<namespace>
kn default
```

## ✅ Validate Resource Location

```bash
# View resources in a specific namespace
kubectl get pods -n <namespace>
```

> [!IMPORTANT]
> Always double-check the namespace before creating or modifying resources!
