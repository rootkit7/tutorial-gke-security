# training-gke-security
This repository is for training of GKE Security

[![Open in Cloud Shell](http://gstatic.com/cloudssh/images/open-btn.png)](https://console.cloud.google.com/cloudshell/open?git_repo=https://github.com/rung/training-gke-security&page=editor&cloudshell_tutorial=README.md)

### Preparation
- Set project id
```bash
gcloud config set project PROJECT_ID
```

- Enable GKE API
```bash
gcloud services enable container.googleapis.com
```

- Create GKE Cluster
```bash
gcloud container clusters create gke-security-testing --zone us-central1-a --machine-type g1-small --num-nodes 3 --async
```

- Get a credential of GKE
```bash
gcloud container clusters get-credentials gke-security-testing --zone=us-central1-a
```

- Testing
```
kubectl get node
```

### Exercise 1: PodSecurityPolicy


### Exercise 2: Workload Identity
- Apply k8s manifest
```
kubectl apply -f manifest -R
```
(Please don't expose deployment on the Internet through Service.)

- Open Web Preview
<img src="img/web-preview.png" width="320">

### (After this training) Clean cluster
```bash
gcloud container clusters delete gke-security-testing --zone us-central1-a --async
```
