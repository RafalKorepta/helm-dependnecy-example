# helm-dependnecy-example

Run the following commands

```
$ helm dependnecy build redpanda-dep
...

$ helm install redpanda-dep redpanda-dep --set redpanda.fullnameOverride=my-name
NAME: redpanda-dep
LAST DEPLOYED: Thu Oct 26 13:27:26 2023
NAMESPACE: default
STATUS: deployed
REVISION: 1
NOTES:
1. Get the application URL by running these commands:
  export POD_NAME=$(kubectl get pods --namespace default -l "app.kubernetes.io/name=redpanda-dep,app.kubernetes.io/instance=redpanda-dep" -o jsonpath="{.items[0].metadata.name}")
  export CONTAINER_PORT=$(kubectl get pod --namespace default $POD_NAME -o jsonpath="{.spec.containers[0].ports[0].containerPort}")
  echo "Visit http://127.0.0.1:8080 to use your application"
  kubectl --namespace default port-forward $POD_NAME 8080:$CONTAINER_PORT

$ kubectl get pod
NAME                                   READY   STATUS      RESTARTS   AGE
my-name-0                              2/2     Running     0          4m24s
my-name-1                              2/2     Running     0          4m24s
my-name-2                              2/2     Running     0          4m24s
my-name-configuration-hkbkp            0/1     Completed   0          4m24s
redpanda-dep-7b4c89df68-7nvck          1/1     Running     0          4m24s
redpanda-dep-console-8859b7cd6-p42rc   1/1     Running     0          4m24s
```