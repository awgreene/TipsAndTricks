# Tips for AWS EKS

## Introduction

## Configuration Commands

List Account Aliases

```bash
$ aws iam list-account-aliases
```

## Connecting kubectl to an existing EKS Cluster
```bash
$ REGION_NAME=
$ CLUSTER_NAME=
$ aws eks --region $REGION update-kubeconfig --name $CLUSTER
```