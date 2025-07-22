# ✅ CKAD Validation Commands

After creating resources, always verify they exist and work as expected.

## 🔍 Basic Checks

```bash
kubectl get pods
kubectl get deployments
kubectl get svc

kubectl describe pod <name>
kubectl describe deployment <name>
```

## 🧪 Inspect Pod Behavior

```bash
# View logs
kubectl logs <pod-name>

# Exec into a pod shell
kubectl exec -it <pod-name> -- /bin/sh
```

## 🌐 Test Network Connectivity

```bash
# Test DNS
kubectl exec -it <pod-name> -- nslookup <service-name>

# Curl a service
kubectl run curlpod --rm -it --image=busybox -- sh
wget <service>:<port>
```

## 📄 Explain YAML Structure

```bash
kubectl explain pod.spec.containers
ke pod  # alias for 'kubectl explain pod --recursive'
```

## 🔥 Clean Up

```bash
kubectl delete pod <name> $now
```
