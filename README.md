## Run in local system

#### Pre-requisites

> `minikube` and `kubectl` should be installed in the local system.
> `minikube start` command should be executed.

#### Steps to run:

Clone the repository and change the directory using below commands

```sh
git clone git@github.com:nvallore/we-connect.git
cd we-connect
```

Check minikube and kubectl are installed

```sh
kubectl version
minikube version
```

Enable required plugins in minikube

```sh
minikube addons enable default-storageclass
minikube addons enable ingress    
minikube addons enable storage-provisioner
minikube addons enable metrics-server
minikube addons enable dashboard
```

Deploy all the kubernetes files

```sh
cd kube
kubectl apply -f .
```


Start a tunnel for ingress

```
minikube tunnel
```

Connect to auth_db in local system to onboard any test data

```
minikube service auth-db --url
Connect to the URL using any DB tools for PostgreSQL with the required credentials.
```

View the dashboard

```
minikube dashboard
```
