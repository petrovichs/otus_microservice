helm install ng ./hello-ch
helm install ng ./hello-ch --dry-run
helm upgrade ng ./hello-ch --set=service.type=LoadBalancer
curl http://192.168.5.5:80


helm list
helm uninstall ng
helm install app ./hello-ch --dry-run
helm repo add bitnami https://charts.bitnami.com/bitnami
helm install pg bitnami/postgresql -f pg_values.yaml


minikube service app-hello-ch --url -n myapp
kubectl config set-context --current --namespace=myapp
kubectl delete all --all

