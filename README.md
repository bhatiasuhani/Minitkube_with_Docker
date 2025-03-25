# Minitkube_with_Docker_on Windows
# ![Minikube Logo](https://upload.wikimedia.org/wikipedia/commons/3/39/Kubernetes_logo_without_workmark.svg)

# Minikube Setup Guide 🚀

Minikube is a tool that helps you run a local Kubernetes cluster on your machine. It's perfect for developers who want to experiment with Kubernetes without setting up a large cloud infrastructure.

## 📌 What is Minikube?
Minikube provides a simple way to start a Kubernetes cluster on a local machine. It works with various drivers like Docker, VirtualBox, and Hyper-V, making Kubernetes accessible for local development, testing, and experimentation.

## ☸️ What is Kubernetes?
Kubernetes is an open-source platform for automating the deployment, scaling, and management of containerized applications. It ensures that applications run reliably and efficiently across different environments.

### Features of Kubernetes:
- Deploy applications in containers across clusters.
- Scale applications up or down effortlessly.
- Manage workloads efficiently with minimal effort.
- Ensure high availability, load balancing, and fault tolerance.

---

## ✅ Step 1: Install Required Tools
Before starting, ensure you have the necessary software installed.

### 1️⃣ Install Docker Desktop 🐋
Minikube can run Kubernetes inside a Docker container. Download and install Docker Desktop from [here](https://www.docker.com/products/docker-desktop/).

During installation:
- Enable WSL 2 backend (recommended). ⚙️
- If you have Windows Pro/Enterprise, enable Hyper-V. 🔧

### 2️⃣ Install Minikube 📦
To install Minikube, open CMD or PowerShell as Administrator and run:
```sh
choco install minikube
```
If you don't have Chocolatey, install Minikube manually from the [official site](https://minikube.sigs.k8s.io/docs/start/).

### 3️⃣ Install kubectl
```sh
choco install kubernetes-cli
```
Verify installation:
```sh
kubectl version --client
```

---

## ✅ Step 2: Start Minikube with Docker Driver 🐳
Ensure that Docker Desktop is running in the background.

### 1️⃣ Start Minikube
```sh
minikube start --driver=docker
```
Check the status:
```sh
minikube status
```

---

## ✅ Step 3: Deploy an Application 🚀
Let's deploy a simple Nginx application in Kubernetes.

### 1️⃣ Create an Nginx Deployment
```sh
kubectl create deployment nginx --image=nginx
```

### 2️⃣ Expose the Deployment 🔓
```sh
kubectl expose deployment nginx --type=NodePort --port=80
```

### 3️⃣ Get the Service URL 🔗
```sh
minikube service nginx --url
```
Open the URL in your browser to see the running Nginx web server. 🌐

---

## ✅ Step 4: Manage Kubernetes Cluster

### 1️⃣ Check Running Pods 📋
```sh
kubectl get pods
```

### 2️⃣ Scale the Deployment 📏
Scale to 3 replicas:
```sh
kubectl scale deployment nginx --replicas=3
```
Check pods again:
```sh
kubectl get pods
```

### 3️⃣ Delete the Deployment 🧹
```sh
kubectl delete service nginx
kubectl delete deployment nginx
```

---

## ✅ Step 5: Stop and Delete Minikube 🗑️

### 1️⃣ Stop Minikube
```sh
minikube stop
```

### 2️⃣ Delete the Cluster
```sh
minikube delete
```
This removes all Kubernetes resources.

---

## 🎯 Conclusion
By using Minikube with Docker, you can run Kubernetes locally without needing Hyper-V or VirtualBox. Docker provides an easy way to manage your cluster and experiment with Kubernetes.

Happy Coding! 🚀😊
