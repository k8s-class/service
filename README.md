# Service

### How do we test a service to make sure its working?

```
[user@phatbox service_only (⎈ |Epick8s:default)]$ kubectl get services
NAME                   TYPE           CLUSTER-IP     EXTERNAL-IP     PORT(S)           AGE
basicnodeapp-service   LoadBalancer   10.0.131.205   104.43.248.36   80:30732/TCP      5d
basicwebapp-service    LoadBalancer   10.0.13.202    23.99.136.60    80:32444/TCP      5d
helloworld-service     NodePort       10.0.36.224    <none>          31001:31001/TCP   2m
kubernetes             ClusterIP      10.0.0.1       <none>          443/TCP           5d

kubectl exec -ti helloworld-deployment-67f66c98cc-bm55d -- /bin/bash

curl http://10.0.36.224:31001

Hello World!

[user@phatbox service (⎈ |Epick8s:default)]$ kubectl exec -ti helloworld-deployment-nodeport-67f66c98cc-krwzr -- /bin/bash
root@helloworld-deployment-nodeport-67f66c98cc-krwzr:/app# curl http://helloworld-service:31001
Hello World!


```
