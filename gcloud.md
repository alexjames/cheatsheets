gcloud get OAuth access token
```
gcloud auth application-default print-access-token
```

Run query
```
curl -H "Authorization: Bearer <token>" https://cloudresourcemanager.googleapis.com/v1beta1/organizations
```
