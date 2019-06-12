# cloudacademyk8s
cloud academy course on k8s

#Setup
To do a quick setup of k8s and access that in WSL on windows follow the steps [here](https://devkimchi.com/2018/06/05/running-kubernetes-on-wsl/)

The k8s single node cluster installed via Docker for Desktop does not include the Kubernetes Dashboard by default but we can always deploy that on our cluster 
```  
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/master/aio/deploy/recommended/kubernetes-dashboard.yaml 
```
To access the kubernetes-dashboard after switching the context
* The dashboard is deployed in kube-system namespace. Find out if its running by 
```
kubectl get pod --namespace=kube-system | grep dashboard
```
* create a NodePort service similar to [this one](https://github.com/agrajm/cloudacademyk8s/blob/master/setup/dashboard-service.yaml) exposing the dashboard
* To sign in to the dashboard follow the steps [here](https://github.com/kubernetes/dashboard/wiki/Access-control#introduction) to get a token 
