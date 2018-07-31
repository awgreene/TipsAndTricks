# Identify kubernetes url
`kubectl proxy --port=8080`

# INTRO TO K8s
## Useful Videos
[Building Helm Charts From the Ground Up: An Introduction to Kubernetes [I] - Amy Chen, Heptio](https://www.youtube.com/watch?v=vQX5nokoqrQ)

# Namespaces
## Get Namespaces
`kubectl get namespaces`

# Nodes
## Get nodes
`kubectl -n {{ NAMESPACE }} get nodes`

# Pods
## Get Pods
`kubectl -n {{ NAMESPACE }} get pods`

## Describe a Pod
`kubectl -n {{ NAMESPACE }} describe pod {{ POD_NAME }}`

## Delete Pods
`kubectl -n {{ NAMESPACE }} delete pods {{ POD_NAME }}`

## Create Pod based off an Image
`kubectl -n {{ NAMESPACE }} run --image={{ IMAGE_NAME }} {{ POD_NAME }}`

# Expose a Service
`kubectl expose -n {{ NAMESPACE}} deployment/{{ DEPLOYMENT_NAME }} --port {{ EXPOSED_PORT }}`

## Create a Proxy
`kubectl proxy`

## Access a Pod through Proxy
http://localhost:8001/api/v1/proxy/namespaces/{{ NAMESPACE }}/service/{{ SERVICE_NAME }}/{{ END_POINT }}
