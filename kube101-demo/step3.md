# Lets run our demo in k8s

Check yaml

`cat kube101-demo.yaml`{{execute HOST1}}

Deploy presentation  `kubectl apply -f kube101-demo.yaml`{{execute HOST1}}


Lets check if our pods are up `kubectl get pods`{{execute HOST1}}

We declared NodePort as 33000 so our service should be listening on https://[[HOST2_SUBDOMAIN]]-33000-[[KATACODA_HOST]].environments.katacoda.com/