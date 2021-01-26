# GCLOUD Cheatsheet

>Disclaimer: This cheatsheet is summarized from personal experience and other online tutorials. It should not be considered as an official reference.

```bash
gcloud auth configure-docker                                           # Authenticate to Google Container Registry
gcloud auth login                                                      # Log in as user 
gcloud container images list-tags [HOSTNAME]/[PROJECT-ID]/[IMAGE]      # Listing the versions of an image in GCR
gcloud container images list --repository=[HOSTNAME]/[PROJECT-ID]      # Listing images by their storage location in GCR
gcloud compute ssl-certificates list                                   # List SSL certs
gcloud auth list                                                       # List credentialed accounts
gcloud config set account [ACCOUNT]                                    # Set active account
```