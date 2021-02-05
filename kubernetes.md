### Confg
```
~/.kube/config
```
## EKS
```
aws eks update-kubeconfig --name <cluster name> --profile <profile with ops role>
```
## GCP
```
gcloud container clusters get-credentials <cluster name> --project <project> --region <region>
```
