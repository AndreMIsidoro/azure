# Azure Container Registry

## Overview

Azure Container Registry (ACR) is a fully-managed, private OCI/Docker registry hosted in Azure for storing and managing container images and other OCI artifacts. Serves as a source of images for AKS, ACI, App Service, Container Apps, CI/CD pipelines (GitHub Actions, Azure DevOps) and Multi-cloud or edge deployments via geo-replication.


## CLI

Create a registry

```shell
az acr create -n myregistry -g rg --sku Standard --admin-enabled false
```