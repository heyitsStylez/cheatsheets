# Azure CLI Cheatsheet

>Disclaimer: This cheatsheet is summarized from personal experience and other online tutorials. It should not be considered as an official reference.

## Azure Container Registry
```bash
az acr login --name myregistry                                         # Login to myregistry
az acr list --output table                                             # List private registries within ACR
az acr repository list --name                                          # List repository
az acr repository show-tags --name --repository                        # Show tags for a repository 
```

## Azure Kubernetes Service
```bash
az aks get-versions --location westeurope --output table                # Get current list of AKS versions
az aks list -o table                                                    # Get list of AKS in subscription
```

## Azure account
```bash
az account set -s PDCockpit                                                 # Set current subscription
```

## Azure account
```bash
 az group list --output table                                          # List resource groups
```