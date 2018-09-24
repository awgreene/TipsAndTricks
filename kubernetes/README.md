# Tips for Kubenetes

# Introduction

# Identify kubernetes url
`kubectl proxy --port=8080`
d
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

## Port Forward to a Pod
kubectl port-forward {{ POD_NAME }} {{ SERVER_PORT }}:{{ POD_PORT }}

## Get rollout history
kubectl rollout history deployment {{ DEPLOYMENT_NAME }}

## Get rollout status
kubectl rollout status deployment {{ DEPLOYMENT_NAME }}

## Revert to a rollout number
kubectl rollout undo deployments/{{ DEPLOYMENT_NAME }} --to-revision={{ REVISION_NUMBER }}

## Scale Replica Set in command line
kubectl scale rs {{ REPLICA_SET_NAME }} --replicas={{ DESIRED_REPLICA_COUNT }}

## Save files to host path
Use the hostPath Volume Plug-in
To relax the security in your cluster so that pods are allowed to use the hostPath volume plug-in without granting everyone access to the privileged SCC:

Edit the restricted SCC:

$ oc edit scc restricted
Add allowHostDirVolumePlugin: true.

Save the changes.

## General Rules for Owner Refs

https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#ownerreference-v1-meta
1) You should ONLY use owner references within the same namespace
2) You should NOT use owner references across namespace boundaries
3) You should NOT use owner references to point to cluster-scoped resources - either from a namespaced resource or other cluster-scoped resources
4) You should NOT use owner references to indicate "i need to know that i created this thing".