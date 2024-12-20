# MISP-Zeek-Kubernetes-Threat-Monitoring

This project integrates MISP (Malware Information Sharing Platform) and Zeek (formerly Bro) within a Kubernetes environment to enhance threat detection and intelligence sharing capabilities. By deploying these tools as Kubernetes workloads, the system offers scalability and efficient management of network security monitoring.

## Features

- **MISP Deployment**: Facilitates the sharing, storing, and correlation of threat intelligence data.
- **Zeek Deployment**: Provides real-time network traffic analysis and monitoring.
- **Kubernetes Integration**: Ensures scalability and efficient resource management.
- **Automated Threat Intelligence Sharing**: Seamless integration between MISP and Zeek for proactive threat detection.

## Prerequisites

- **Kubernetes Cluster**: Ensure you have a running Kubernetes cluster with at least one control plane and one worker node.
- **Helm**: Package manager for Kubernetes applications.
- **Docker**: Container runtime for building and managing container images.

## Deployment Steps

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/RK45516/MISP-Zeek-Kubernetes-Threat-Monitoring.git
   cd MISP-Zeek-Kubernetes-Threat-Monitoring

2. **Set Up Environment Variables**:

   Copy the template.env to .env and modify the variables as needed.

   cp template.env .env

3. Deploy MISP:

  Apply the Persistent Volume Claims:
    kubectl apply -f misp-core-claim0-persistentvolumeclaim.yaml
    kubectl apply -f misp-core-claim1-persistentvolumeclaim.yaml
   Apply other PVCs as needed

4. Deploy MISP Core:

   kubectl apply -f misp-core-deployment.yaml
   kubectl apply -f misp-core-service.yaml

5. Deploy MISP Modules:

   kubectl apply -f misp-modules-deployment.yaml

6. Deploy Zeek:

    Build the Docker image:

      docker build -f builder.Dockerfile -t zeek-builder .
      docker build -f final.Dockerfile -t zeek-final .

7. Deploy Zeek using Docker Compose:

      docker-compose up -d

8. Verify Deployments:

  Check the status of the pods:

  kubectl get pods

Ensure all pods are running without issues.

Access MISP:

Retrieve the external IP of the MISP service:

kubectl get svc misp-core
Access MISP via the obtained IP address.

Configuration

MISP:

Configure MISP settings through the web interface as per your requirements.

Zeek:

Modify Zeek configuration files as needed to tailor network monitoring.

Contributing
Contributions are welcome! Please fork the repository and submit a pull request for any enhancements or bug fixes.

License
This project is created only as an idea and it is still work in progress. Any copyright claims for the idea will need to fight me and my professor over it.

Acknowledgments
Special thanks to the open-source community for their invaluable tools and resources that made this integration possible. Specifal thanks to my professor for this research


This README provides an overview of the project, prerequisites, deployment steps, configuration guidance, and other essential information to help users set up and understand the MISP-Zeek-Kubernetes-Threat-Monitoring system.

 
