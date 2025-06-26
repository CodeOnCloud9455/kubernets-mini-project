 Employee Management Django App on Kubernetes body { font-family: Arial, sans-serif; line-height: 1.6; margin: 40px; max-width: 800px; } code { background-color: #f4f4f4; padding: 2px 4px; font-size: 0.95em; border-radius: 4px; } pre { background-color: #f4f4f4; padding: 12px; border-radius: 6px; overflow-x: auto; } h1, h2, h3 { color: #2c3e50; }

Employee Management Django App on Kubernetes
============================================

This project contains the Kubernetes manifests required to deploy a Django-based Employee Management application using Docker and Kubernetes.

Project Structure
-----------------

*   `namespace.yml` – Defines a namespace for isolating the application.
*   `deployment.yml` – Deploys the Django application as a Kubernetes Deployment with two replicas.
*   `service.yml` – Exposes the Django application within the cluster using a ClusterIP service.

Prerequisites
-------------

*   Kubernetes cluster (Minikube, Kind, or any cloud provider)
*   `kubectl` configured and connected to your cluster
*   Docker (if building images locally)

Deployment Steps
----------------

### 1\. Create the Namespace

    kubectl apply -f namespace.yml

### 2\. Deploy the Application

    kubectl apply -f deployment.yml

### 3\. Create the Service

    kubectl apply -f service.yml

### 4\. Port Forward to Access the Application

    kubectl port-forward svc/django-app-svc -n emp-app 8000:8000

### 5\. Access the App

Open your browser and go to: [http://localhost:8000](http://localhost:8000)

Acknowledgments
---------------

Special thanks to the developer of the Docker image `[memorydrive/employee-management](https://github.com/syn606)` for making this application deployment-ready.
