# Identify kubernetes url
`kubectl proxy --port=8080`

# INTRO TO K8s
## Useful Videos
[Building Helm Charts From the Ground Up: An Introduction to Kubernetes [I] - Amy Chen, Heptio](https://www.youtube.com/watch?v=vQX5nokoqrQ)

# Namespaces
## Get Namespaces
`kubectl get namespaces`

# Pods
## Get Pods
`kubectl -n <NAMESPACE> get pods`

## Describe a Pod
`kubectl -n <NAMESPACE> describe pod <POD_NAME>`

## Delete Pods
`kubectl -n <NAMESPACE> delete pods <POD_NAME>`
