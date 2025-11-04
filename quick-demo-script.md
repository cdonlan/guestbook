# Quick Guestbook ArgoCD Demo Script
*5-minute lightning demo*

## Pre-Demo Setup
- ArgoCD UI open in browser
- Terminal ready with kubectl
- Repository tab open in GitHub

---

## Demo Flow

### 1. The Problem (30 seconds)
*"Traditional deployments: manual kubectl applies, configuration drift, no audit trail"*

### 2. The Solution - GitOps (30 seconds)
*"Git as single source of truth. ArgoCD watches Git, automatically syncs to Kubernetes"*

### 3. Show the Code (1 minute)
**GitHub Repository:**
- 4 simple files
- ArgoCD Application points to this repo
- Standard Kubernetes manifests (Deployment + Service)

### 4. ArgoCD UI (2 minutes)
**Show in ArgoCD dashboard:**
- ✅ Healthy & Synced status
- Click into app → Resource tree view
- *"ArgoCD automatically deployed from Git"*

### 5. GitOps Magic (1.5 minutes)
**Live change:**
1. Edit deployment: `replicas: 1` → `replicas: 3`
2. Commit & push to GitHub
3. Watch ArgoCD auto-sync in real-time
4. See new pods spinning up

### 6. Self-Healing Demo (30 seconds)
**Manual change:**
```bash
kubectl scale deployment guestbook-ui --replicas=5 -n guestbook
```
*"Watch ArgoCD detect drift and automatically revert to Git state"*

### 7. Wrap-up (30 seconds)
**Benefits delivered:**
- ✅ Automated deployments
- ✅ Configuration drift prevention  
- ✅ Complete audit trail via Git
- ✅ Easy rollbacks

*"GitOps: Your cluster always matches Git. Simple, powerful, reliable."*

---

## Quick Commands Reference
```powershell
# Scale manually (for drift demo)
kubectl scale deployment guestbook-ui --replicas=5 -n guestbook

# Check application status
kubectl get pods -n guestbook

# Watch pods in real-time (PowerShell)
kubectl get pods -n guestbook -w

# Access the app locally
kubectl port-forward svc/guestbook-ui 8080:80 -n guestbook
```

## One-Liner Value Prop
*"GitOps with ArgoCD: Git commit becomes Kubernetes deployment, automatically and reliably."*