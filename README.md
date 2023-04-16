# Deploying Nginx in a Kubernetes cluster using kinD, Helm and Terraform


Deploying an Nginx container on a kubernetes cluster using kinD (Kubernetes in Docker). The service is deployed behind a load balancer and supports multiple replicas using Helm to manage all the packages. This project is deployed using Terraform.

<br />

## **Technologies used:**

- [Nginx](https://www.nginx.com/)
- [Kubernetes CLI - Kubectl](https://kubernetes.io/docs/tasks/tools/)
- [kinD](https://kind.sigs.k8s.io/)
- [Helm](https://helm.sh/)
- [Terraform](https://www.terraform.io/)

<br />

## **Project structure:**

- **build/** ---> docker images
- **lattice/** ---> helm charts
- **terraform/** ---> terraform related
  - The `terraform/` directory contains the main configuration files for the Terraform project: `main.tf`, `variables.tf`, and `outputs.tf`. These files define the infrastructure resources, variables, and outputs respectively.
    - The `provider.tf` file specifies the provider that Terraform will use to create the infrastructure. This file should also include any provider-specific configuration.

    - The `terraform.tfvars` file is used to define variables that are specific to the Terraform project. This file should be version-controlled.

    - The `backend.tf` file specifies the backend configuration for storing Terraform state. This file should also include any backend-specific configuration.

  - The `modules/` directory contains subdirectories for each module in the Terraform project. Each module should have a `main.tf`, `variables.tf`, and `outputs.tf` file that define the resources, variables, and outputs respectively.

  - The `envs/` directory contains subdirectories for each environment that the Terraform project will be deployed to. Each environment directory should contain a `main.tf` file that defines the resources for that environment, and a `variables.tfvars` file that defines the environment-specific variable values.