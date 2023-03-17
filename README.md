# Балование с кубером

## Проект

* Python 3.11
* Django
* PostgreSQL

## Запуск

```bash
minikube start
minikube addons enable registry
minikube addons enable ingress

kubectl apply -f kubernetes/postgres.yml
kubectl apply -f kubernetes/django.yml

kubectl create secret generic postgres-credentials --from-literal=user=u --from-literal=password=b
```
