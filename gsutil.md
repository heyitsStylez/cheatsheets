# GSUTIL Cheatsheet

>Disclaimer: This cheatsheet is summarized from personal experience and other online tutorials. It should not be considered as an official reference.

```bash
gsutil cp [OBJECT_LOCATION] gs://[DESTINATION_BUCKET_NAME]/                                     # Copy object to bucket
gsutil rm gs://[BUCKET_NAME]/[OBJECT_NAME]                                                      # Delete object from bucket
gsutil ls -r gs://[BUCKET_NAME]/**                                                              # List all objects in bucket
gsutil cp -r "gs://[SOURCE_BUCKET]/uploads/Training Deck" gs://[DESTINATION_BUCKET]/uploads     # Copy folder Training Deck recursively to folder uploads
gsutil -m acl ch -u AllUsers:R -r gs://[BUCKET_NAME]/icaracademy                                # Recursively make all objects in icaracademy folder public read
```