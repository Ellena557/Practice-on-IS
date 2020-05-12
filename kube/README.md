1. clean a minikube machine and start a new one:
```
minikube delete
minikube start 
kubectl config use-context minikube
```

2. use dashboard:
```
minikube dashboard
```

3. create postgres staff:
```
kubectl create -f postgres.yaml
```

4. before using docker:
```
eval $(minikube docker-env)
```

5. create docker containers with docker-compose or commands like:
```
docker build -t docker-rbc . 
docker build -t docker-ml .
docker build -t docker-weather .
```

6. create pods and expose services:
```
kubectl create -f deployment-weather.yaml
kubectl expose deployment kube-weather --type=LoadBalancer --port=8070
```

```
kubectl create -f deployment-rbc.yaml
kubectl expose deployment kube-rbc --type=LoadBalancer --port=8060
```

```
kubectl create -f deployment-ml.yaml
kubectl expose deployment kube-ml --type=LoadBalancer --port=8050
```
