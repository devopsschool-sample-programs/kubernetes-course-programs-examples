# Setting up the dashboard

## Start dashboard

Create dashboard:
```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/master/src/deploy/recommended/kubernetes-dashboard.yaml
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/master/src/deploy/recommended/kubernetes-dashboard.yaml
```

## Create user

Create sample user (if using RBAC - on by default on new installs with kops / kubeadm):
```
kubectl create -f sample-user.yaml

```

## Get login token:
```
kubectl -n kube-system get secret | grep admin-user
kubectl -n kube-system describe secret admin-user-token-<id displayed by previous command>
kubectl -n kube-system describe secret admin-user-token-lp544
```
kubectl config view 

## Login to dashboard
Go to http://api.yourdomain.com:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/#!/login

Login: admin
Password: the password that is listed in ~/.kube/config (open file in editor and look for "password: ..."

Choose for login token and enter the login token from the previous step

EKS DASHBOARD
https://docs.aws.amazon.com/eks/latest/userguide/dashboard-tutorial.html

eyJhbGciOiJSUzI1NiIsImtpZCI6IiJ9.eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhY2NvdW50Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9uYW1lc3BhY2UiOiJrdWJlLXN5c3RlbSIsImt1YmVybmV0ZXMuaW8vc2VydmljZWFjY291bnQvc2VjcmV0Lm5hbWUiOiJla3MtYWRtaW4tdG9rZW4taHQ4NXoiLCJrdWJlcm5ldGVzLmlvL3NlcnZpY2VhY2NvdW50L3NlcnZpY2UtYWNjb3VudC5uYW1lIjoiZWtzLWFkbWluIiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZXJ2aWNlLWFjY291bnQudWlkIjoiZjM1OTg0YTctODUxYi0xMWU4LTk0MzItMDJiNzYxYzBkZWFjIiwic3ViIjoic3lzdGVtOnNlcnZpY2VhY2NvdW50Omt1YmUtc3lzdGVtOmVrcy1hZG1pbiJ9.OO06BOFwCkITe9wXQgAnB65KbEri6aKvGzX6jtmRbpI2z6I3JAYUq1K0-eIpyqHuPuVkq5C184NEnxBBJgbueQVFXcxYLSrvTv1uEXy7OYNYgmShk-9IKjqlzIRZXuvC96maIlIfipFKND5re7k7nPozm4GrlvF5L4YeGh5JuTy8gMY27qG_pAxl0At_Oknw4Ln0hZo-Va7UObuEd-y53nS2EjhELarUIejaHRTJ-tV2ZRxwPPBYStP2m7PeVI1wfCGhr39hwIpRz0dyTKXLbF55PKLOazUbf8CMdzO1NdXg18Xli3UFHn47p8egRUCfmcSmWyYgZ8KZU9vKXWBAUQ


http://35.163.198.21:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/

kubectl proxy --address='0.0.0.0' --port=8002 --accept-hosts='.*'

https://github.com/kubernetes/dashboard/wiki/Accessing-Dashboard---1.7.X-and-above#kubectl-proxy



https://github.com/kubernetes/dashboard/wiki/Accessing-Dashboard---1.7.X-and-above#kubectl-proxy



https://34.221.37.114:31815/#!/overview?namespace=default




