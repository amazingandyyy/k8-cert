# kubectl commands

## Commands

```shell
$ kubectl run --generator=run-pod/v1 redis --image=redis:alpine -l tier=db --dry-run -o yaml
$ kubectl run --generator=run-pod/v1 nginx-pod --image=nginx:alpine --dry-run -o yaml
$ kubectl expose pod redis --port=6379 --name redis-service

$ kubectl get deployment
NAME     READY   UP-TO-DATE   AVAILABLE   AGE
webapp   1/1     1            1           25s
$ kubectl scale deployment webapp --replicas=3

Expose the webapp as service webapp-service application on port 30082 on the nodes on the cluster


The web application listens on port 8080
Run the command kubectl expose deployment webapp --type=NodePort --port=8080 --name=webapp-service --dry-run -o yaml > webapp-service.yaml to generate a service definition file. Then edit the nodeport in it and create a service.

kubectl config set-context $(kubectl config current-context) --namespace=devvv

kubectl taint nodes node01 spray=mortein:NoSchedule
kubectl taint nodes master node-role.kubernetes.io/master:NoSchedule-
kubectl run mosquito --image=nginx --dry-run -o yaml > pod.yaml
kubectl get pods -o wide

kubectl label nodes node-1 size=Large # then use nodeSelector in pod-definition.yaml
kubectl get pods -o wide
# affinity: https://raw.githubusercontent.com/kubernetes/website/master/content/en/examples/pods/pod-with-node-affinity.yaml
# readinessProbe: https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/#define-readiness-probes
# livenessProbe: https://raw.githubusercontent.com/kubernetes/website/master/content/en/examples/pods/probe/http-liveness.yaml
```

