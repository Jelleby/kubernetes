# kubernetes

## Create Deployments with kubectl

```
kubectl create deployment kubernetes-bootcamp --image=gcr.io/google-samples/kubernetes-bootcamp:v1
```

You can create from the start a Deployment with multiple instances using the **--replicas** parameter for the kubect create deployment command

## Create Service for it with kubectl
```
kubectl expose deployment/kubernetes-bootcamp --type="LoadBalancer" --port 8080
```
- If you want to use replicas etc you should use type LoadBalancer

## Scale Deployments with kubectl
```
kubectl scale deployments/kubernetes-bootcamp --replicas=4
```

## Perform a Rolling Update on Deployment

### Update the image of an application with *set image*
```
kubectl set image deployments kubernetes-bootcamp kubernetes-bootcamp=docker.io/jocatalin/kubernetes-bootcamp:v2
```

### Confirm updates by rollout status command
```
kubectl rollout status deployment kubernetes-bootcamp 
```

### Undo Rollout (e.g if something does not work)
```
kubectl rollout undo deployment kubernetes-bootcamp
```

## Troubleshooting with Kubectl

The most common opertions can be done with:

- kubectl get - list resources
- kubectl describe - show detailed information, about a resource
- kubectl logs - print the logs from a container in a pod
- kubectl exec - execute a command on a container in a pod


## Useful commands random

- kubectl describe pods - show detailed infos from all pods in ns
```
kubectl exec -it kubernetes-bootcamp-9bc58d867-tr2kl -- bash
```
Similar to the docker exec -it but with dash ( -- bash )

kubectl get pods -l app=kubernetes-bootcamp (filter with label)



## Hints for Structuring README Files

- Use `#`, `##`, `###` for headings to organize sections.
- Use bullet points (`-` or `*`) for lists.
- Use code blocks with triple backticks (```) for code or command examples.
- Use **bold** or *italic* for emphasis.
- Add sections like:
  - Project Description
  - Installation
  - Usage
  - Contributing
  - License
- Keep sections concise and relevant.