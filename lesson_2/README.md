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
minikube docker-env
kubectl config set-context --current --namespace=myapp
kubectl delete all --all



mvn clean install
docker build -t gorshkovpsergey/nsi:v1 .
helm uninstall app
helm install app ./hello-ch





export NODE_PORT=$(kubectl get services/app-hello-ch -o go-template='{{(index .spec.ports 0).nodePort}}')
echo NODE_PORT=$NODE_PORT
curl $(minikube ip):$NODE_PORT/config
