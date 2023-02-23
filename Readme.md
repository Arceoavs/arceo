# Pocketbase Kubernetes Deployment

This repository contains Kubernetes resources for deploying a Pocketbase service using the Kustomize tool.

## Prerequisites

- Access to a Kubernetes cluster
- Domain name pointing to the cluster

## Contents

The repository contains the following resources:

- `base` directory: This directory contains the base resources for the Pocketbase service, including a Deployment, a Service, an Ingress, a Namespace, and a PersistentVolumeClaim.
- `overlays` directory: This directory contains overlays for the Pocketbase service. No overlays are provided by default, but you can create your own overlays to customize the service.

## Usage

To deploy the Pocketbase service, follow these steps:

1. Install Kustomize: https://kubectl.docs.kubernetes.io/installation/kustomize/
2. Clone this repository

   ```bash
   git clone <repo-url>
   ```

3. Navigate to the overlays directory for your desired environment
   ```bash
    cd overlays/production
   ```
4. Customize the resources in the overlay directory as needed by editing the corresponding `kustomization.yaml` file.
5. Deploy the resources using Kustomize

   ```bash
   kustomize build . | kubectl apply -f -
    #OR
    kubectl apply -k .
   ```

6. Verify that the resources were deployed successfully

   ```bash
   kubectl get all -n pocketbase
   ```

## Contributing

Contributions to the Pocketbase Kubernetes Deployment repository are welcome.
