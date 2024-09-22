# Nginx Helm Chart

This Helm chart deploys an Nginx server on Kubernetes with optional HTTPS support.

## Prerequisites

- Kubernetes 1.16+
- Helm 3.0+
- Cert-manager v1.0+ (for HTTPS support)

## Installing the Chart

To install the chart with the release name `my-nginx`:

```bash
# Add the Jetstack Helm repository (for cert-manager)
helm repo add jetstack https://charts.jetstack.io

# Update your local Helm chart repository cache
helm repo update

# Install cert-manager (if not already installed)
helm install cert-manager jetstack/cert-manager --namespace cert-manager --create-namespace --version v1.7.1 --set installCRDs=true

# Install the Nginx chart
helm install my-nginx ./nginx-helm-chart