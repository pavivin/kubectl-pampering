# Балование с кубером

## Проект

* Django (Python 3.11)
  * Pod Deployment
* PostgreSQL
  * Pod Deployment => StatefulSet
* Ingress
  * Nginx-controller

In progress:

* Helm
* StatefulSet

## Запуск

```bash
minikube start
minikube addons enable registry
minikube addons enable ingress

kubectl apply -f kubernetes/postgres.yml
kubectl apply -f kubernetes/django.yml

kubectl create secret generic postgres-credentials --from-literal=user=u --from-literal=password=b
```

## Обновить приложение

```bash
docker build .
docker push REGISTRY_NAME
docker pull REGISTRY_NAME
```
