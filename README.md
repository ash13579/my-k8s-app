# My First Kubernetes Deployment on Minikube

This project is a hands-on exercise to understand the fundamentals of deploying and managing a simple application on a local Kubernetes cluster using Minikube.

## 📝 Project Overview

The goal of this project is to deploy a basic Nginx "Hello World" web server. The process involves creating two key Kubernetes objects:
1.  A **Deployment** to define the desired state of our application (e.g., run 2 replicas).
2.  A **Service** to expose the application to be accessible from outside the cluster.

---

## 🛠️ Tools Used

* **Minikube:** To run a single-node Kubernetes cluster locally.
* **kubectl:** The command-line tool for interacting with the Kubernetes cluster.
* **Docker:** As the container runtime used by Minikube to run the application containers.

---

## 📁 Project Structure

The repository contains the core Kubernetes configuration files:

.├── deployment.yaml   # Defines the Deployment to run the Nginx pods├── service.yaml      # Defines the Service to expose the pods└── README.md         # This file
---

## 🚀 How to Run

To get this project up and running on your local machine, follow these steps:

1.  **Start the Cluster:**
    Ensure Minikube is installed and running, then start your local cluster.
    ```bash
    minikube start
    ```

2.  **Apply the Deployment:**
    This command reads the `deployment.yaml` file and instructs Kubernetes to create the pods.
    ```bash
    kubectl apply -f deployment.yaml
    ```

3.  **Apply the Service:**
    This command creates the network service to expose the pods.
    ```bash
    kubectl apply -f service.yaml
    ```

4.  **Access the Application:**
    This Minikube command will automatically open a browser window pointed at your running application.
    ```bash
    minikube service my-web-app-service
    ```

---

## ✨ Key Commands for Verification

Throughout this project, several `kubectl` commands were used to check the status and manage the application:

* **Check running pods:**
    ```bash
    kubectl get pods
    ```
* **Get detailed information about a pod (for troubleshooting):**
    ```bash
    # Replace <pod-name> with the actual name of your pod
    kubectl describe pod <pod-name>
    ```
* **Scale the number of running pods:**
    ```bash
    # Example to scale to 4 replicas
    kubectl scale deployment my-web-app-deployment --replicas=4
    ```
* **View logs from a specific pod:**
    ```bash
    # Replace <pod-name> with the actual name of your pod
    kubectl logs <pod-name>
    ```
