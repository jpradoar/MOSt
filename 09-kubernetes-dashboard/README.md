# Kubernetes Dashboard

<br>

### Deploying the Dashboard UI
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.5.0/aio/deploy/recommended.yaml

<br>

### Create a admin user (you can edit this file and create your own user)
 kubectl apply -f 00-kubernetes-dashboard-eks-admin-service-account.yaml

<br>

### Get Token
 - kubectl -n kubernetes-dashboard get secret $(kubectl -n kubernetes-dashboard get sa/admin-user -o jsonpath="{.secrets[0].name}") -o go-template="{{.data.token | base64decode}}"

<br>
<img src="overview.png">
<br>
<img src="overview.png">
<br>


### If you need to delete it
 -  kubectl delete -f 00-kubernetes-dashboard-eks-admin-service-account.yaml