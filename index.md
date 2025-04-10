# 💜 DevOps Cheatsheet – Podman, Minikube, Kubernetes, Docker

A complete beginner-friendly Markdown cheatsheet with essential commands, YAML examples, and deployment flow.

---

## 📚 Core Concepts

| 📌 Term      | 🧠 Meaning |
|-------------|------------|
| **🖼️ Image** | A snapshot of an app and its dependencies. |
| **📦 Container** | A running instance of an image. |
| **🧱 Pod** | Smallest deployable unit in Kubernetes. Can hold one or more containers. |
| **🖥️ Node** | A worker machine in Kubernetes (physical/virtual). |
| **🧩 Cluster** | A set of nodes managed by Kubernetes. |
| **🌐 Service** | Exposes pods to the network. |
| **🛠️ Deployment** | Tells Kubernetes how to deploy and manage pods. |

---

## 🐳 Podman Commands

### 🚀 Basic Commands

```bash
podman --version                     # Check Podman version
podman info                          # System info
podman images                        # List images
podman search <image>               # Search images
podman pull <image>                 # Pull image
podman rmi <image>                  # Remove image
```

### 📦 Container Management

```bash
podman run -it <image>              # Run interactive container
podman run -d -p 8080:80 <image>    # Run web server container (map port)
podman ps                           # List running containers
podman ps -a                        # List all containers
podman stop <container_id>          # Stop container
podman rm <container_id>            # Remove container
podman logs <container_id>          # View logs
podman exec -it <id> <cmd>          # Run command in container
```

### 🛠️ Build & Push

```bash
podman build -t myimage .                            # Build image from Dockerfile
podman tag myimage docker.io/user/myimage:latest     # Tag image for registry
podman push docker.io/user/myimage:latest            # Push image to Docker Hub
```

---

## 📦 Minikube Commands

```bash
minikube start                                       # Start Minikube cluster
minikube stop                                        # Stop cluster
minikube delete                                      # Delete cluster
minikube status                                      # Show status
minikube dashboard                                   # Launch dashboard
minikube service <service-name> --url                # Get NodePort service URL
```

> 🧰 Use Podman as runtime (optional):
```bash
minikube start --driver=podman
```

---

## ☸️ Kubernetes Commands

```bash
kubectl version                                      # Check kubectl version
kubectl cluster-info                                 # Info about cluster
kubectl get nodes                                    # Show nodes
kubectl get pods                                     # Show pods
kubectl get services                                 # Show services
kubectl get deployments                              # Show deployments
kubectl describe pod <pod_name>                      # Describe pod
kubectl delete pod <pod_name>                        # Delete pod
kubectl apply -f <file>.yaml                         # Apply YAML file
kubectl port-forward svc/<service-name> 8080:80      # Port forward to service
```

---

## 📝 YAML File Examples

### 📄 Deployment YAML

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: myapp
spec:
  replicas: 1
  selector:
    matchLabels:
      app: myapp
  template:
    metadata:
      labels:
        app: myapp
    spec:
      containers:
      - name: mycontainer
        image: user/myimage:latest
        ports:
        - containerPort: 80
```

Apply:
```bash
kubectl apply -f deployment.yaml
```

### 🌐 Service YAML

```yaml
apiVersion: v1
kind: Service
metadata:
  name: myapp-service
spec:
  selector:
    app: myapp
  ports:
  - protocol: TCP
    port: 80
    targetPort: 80
  type: NodePort
```

Apply:
```bash
kubectl apply -f service.yaml
```

Get service URL:
```bash
minikube service myapp-service --url
```

---

## 🐋 Docker Image Push

```bash
docker login
podman build -t myimage .
podman tag myimage docker.io/username/myimage:latest
podman push docker.io/username/myimage:latest
```

---

## 🔁 DevOps Flow (Quick Map)

```text
🧑‍💻 Code → 🐋 Dockerfile → 🛠️ Build Image → ✅ Test Locally (Podman) → 📤 Push Image → ☸️ Minikube (K8s) → 📄 YAML → 🚀 Deploy → 🌐 Service → 🌍 Access via NodePort
```

🚀 Happy Shipping from **Tech Quanta** 💜

