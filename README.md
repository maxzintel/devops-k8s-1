# devops-k8s-1
Practicing DevOps principles with K8s, vol 1.

## Software used:
#### Windows:
  * docker
  * kubectl
  * minikube
  * hyperV as VM Driver

## Notes about Containerization:
  * Limit to one process per container. Ex: your database is one set (cluster) of containers, your express server is another. Combining these two processes into one massive container is bad practice and is generally contrary to the philosophy behind containerization.
  * Data within a container is not preserved by default. Meaning, if you stop a container (and it has no backups, ebs volumes, etc...), all changes that occurred within that container are lost.

## Docker Cheatsheet:
  * Build image: `docker build .`
  * Build & Tag: `docker build -t user/name:latest .`
  * Tag image: `docker tag imageid user/name`
  * Push image: `docker push user/name`
  * List images: `docker images`
  * List all containers: `docker ps -a`

## K8s Cheatsheet:
  * `kubectl get pod`: Get information about all running pods
  * `kubectl describe pod <pod>`: Describe one pod
  * `kubectl expose pod <pod> --port=444 --name=frontend`: Expose the port of a pod (creates a new service)
  * `kubectl port-forward <pod> 8080`: Port forward the exposed pod port to your local machine
  * `kubectl attach <podname> -i`: Attach to the pod
  * `kubectl exec <pod> -- command`: Execute a command on the pod
  * `kubectl label pods <pod> mylabel=NotALabel`: Add a new label to a pod
  * `kubectl run -i --tty busybox --image=busybox --restart=Never -- sh`: Run a shell in a pod - very useful for debugging, connect to malfunctioning pod.
  * `kubectl get deployments`: Get information on current deployments
  * `kubectl get rs`: Get information about the replica sets
  * `kubectl get pods --show-labels`: get pods, and also show labels attached to those pods
  * `kubectl rollout status deployment/helloworld`: Get deployment status
  * `kubectl set image deployment/helloworld k8s-demo=k8s-demo:2`: Run k8s-demo with the image label version 2
  * `kubectl edit deployment/helloworld`: Edit the deployment object
  * `kubectl rollout status deployment/helloworld`: Get the status of the rollout
  * `kubectl rollout history deployment/helloworld`: Get the rollout history
  * `kubectl rollout undo deployment/helloworld`: Rollback to previous version
  * `kubectl rollout undo deployment/helloworld --to-revision=n`: Rollback to any version version
