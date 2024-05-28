source : https://www.red-gate.com/simple-talk/homepage/how-to-set-up-jenkins-ci-cd-on-kubernetes-cluster-using-helm/

## installation

````
helm repo add jenkins https://charts.jenkins.io
helm repo update
helm install myjenkins jenkins/jenkins
kubectl exec --namespace default -it svc/myjenkins -c jenkins – 
/bin/cat /run/secrets/chart-admin-password && echo
kubectl --namespace default port-forward svc/myjenkins 8080:8080
```

## 