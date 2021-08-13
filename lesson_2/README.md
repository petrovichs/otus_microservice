https://kubernetes.io/ru/docs/reference/kubectl/cheatsheet/

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



helm uninstall userservice
cd ../../user/
docker build -t gorshkovpsergey/user:v1 .
cd ../otus_microservice/lesson_2/
helm install userservice ./user-service


helm uninstall nsiservice
cd ../../nsi/
mvn clean install
docker build -t gorshkovpsergey/nsi:v1 .
cd ../otus_microservice/lesson_2/
helm install nsiservice ./nsi-service



helm uninstall userservice
helm install userservice ./user-service


   19  docker build -t gorshkovpsergey/nsi:v1 .
   20  docker push gorshkovpsergey/linked/nsi:v1
   21  docker push gorshkovpsergey/nsi:v1

newman


helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm install prom prometheus-community/kube-prometheus-stack -f prometheus.yaml
kubectl port-forward -n myapp service/prom-kube-prometheus-stack-prometheus 9090
kubectl port-forward -n myapp service/prom-grafana 9000:80

