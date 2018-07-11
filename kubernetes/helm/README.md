# Helm Tips and Tricks

## Role-based Access Control
`kubectl create -f rbac-config.yaml`

## Run tiller with a specific user account
`helm init --tiller-image=gcr.io/kubernetes-helm/tiller:v2.9.1 --service-account tiller`

## Delete Tiller from K8s Cluster
`helm reset --force`
