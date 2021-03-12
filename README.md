# Sharing Storage and Pod Affinity

This repo has sample deployments and a cronjob sharing vsphere storage using 
pod affinity.

Use `custom-storage-class.yaml` to create a new storage class named
`vsan-retain-storage-policy` with the retain policy set to `Retain` (default is
Delete).

There is also an example of manually provisioning the persistent volume in 
`pv.yaml`, but that is not necessary, because the pvc will dynamically
provision the volume. 

There are two yaml files named `deploy-0.yaml` and `deploy-1.yaml`.  These are 
identical deployments named differently and using different storage.

## Deployment Steps

1. `kubectl apply -f custom-storage-class.yaml`
1. `kubectl apply -f deploy-0.yaml`
1. `kubectl apply -f deploy-1.yaml`
