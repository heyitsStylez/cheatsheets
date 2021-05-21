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

## Create Instance
```bash
gcloud compute instances create [INSTANCE_NAMES] \
  --zone=asia-southeast1-a \
  --subnet=default \
  --tags [TAGS] \
  --machine-type=[MACHINE_TYPE]
  --image-family [IMAGE_FAMILY] \
  --image-project [IMAGE_PROJECT] \
  --create-disk size=[SIZE_GB],type=[DISK_TYPE]
```

gcloud compute instances create preprod-mongo0 preprod-mongo1 preprod-mongo2 \
  --zone=asia-southeast1-a \
  --subnet=default \
  --tags office-malaysia \
  --machine-type=n1-standard-1 \
  --image-family debian-9 \
  --image-project debian-cloud \
  --create-disk size=50GB,type=pd-ssd