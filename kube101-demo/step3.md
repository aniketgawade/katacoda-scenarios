## Lets run our demo in k8s

Check yaml

`cat kube101-demo.yaml`{{execute HOST1}}

Deploy presentation  `kubectl apply -f kube101-demo.yaml`{{execute HOST1}}


Lets check if our pods are up `kubectl get pods`{{execute HOST1}}

We declared NodePort as 30003 so our service should be listening on https://[[HOST2_SUBDOMAIN]]-30003-[[KATACODA_HOST]].environments.katacoda.com/

Services: 

`kubectl get services`{{execute HOST1}}

`kubectl describe svc/kube101`{{execute HOST1}}

Deployment: 

`kubectl get deployment`{{execute HOST1}}

`kubectl describe  deployment/kube101`{{execute HOST1}}

Lets delete all our pods

`kubectl get pods | awk '{print $1}' | egrep -v NAME | xargs kubectl delete pod`{{execute HOST1}}

Redis:


`kubectl run redis --image=redis --replicas=3 --port=6379`{{execute HOST1}}

`kubectl expose deployment/redis --port=8099 --target-port=6379`{{execute HOST1}}


Exec into container

`kubectl exec -it {pod_id} bash`{{execute HOST1}}


Get all

`kubectl get pods,deployment,service`{{execute HOST1}}

Lets head back to our presentation:

https://[[HOST2_SUBDOMAIN]]-30003-[[KATACODA_HOST]].environments.katacoda.com/#frame3390
