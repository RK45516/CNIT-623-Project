# MISP ZEEK Kubernetes Threat Monitoring Idea

Create 3 instances on your bare-metal cloud of any choice (FABRIC, Chameleon). The minimum specifications necessary to be able to deploy this setup is

VM 1: Control Node
Specs: 8 vCPU, 16 GB RAM, 128 GB Storage

VM 2: Worker Node
Specs: 8 vCPU, 16 GB RAM, 128 GB Storage

VM 3: MariaDB/Redis Node
Specs: 8 vCPU, 16 GB RAM, 512 GB Storage

Please refer to the github project (https://github.com/MISP/misp-docker) for more details in terms of setting up MISP using a pre-built docker image. For this project, MISP dockerfiles were converted into a Kubernetes Manifest using Kompose.

Please refer to the github project (https://github.com/zeek/zeek-docker) for more details in terms of setting up Zeek using a pre-built docker image. For this project, Zeek dockerfiles were converted into Kubernetes Manifest using Kompose.


Steps for setup:
- Control node has to be setup using 
