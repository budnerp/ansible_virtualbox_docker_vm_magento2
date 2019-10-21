## Notes
Possible booting sequence. Possibly for initial execution:
```
minikube config set memory 4096
minikube config set cpus 2
minikube start
```

## `minikube`
Access the kubernetes dashboard running within the minikube cluster
```
minikube dashboard
```

Expose <deploymemnt-name> Deployment as a Service:
```
kubectl expose deployment <deploymemnt-name> --type=NodePort --port=8080
```

Check if the Pod is up and running:
```
kubectl get pod
```

Get the URL of the exposed Service:
```
minikube service <deploymemnt-name> --url
```

Stop the local Minikube cluster:
```
minikube stop
```

You can specify the version of Kubernetes for Minikube to use by adding the --kubernetes-version string to the minikube start command. For example, to run version v1.16.0, you would run the following:
```
minikube start --kubernetes-version v1.16.0
```

Check minikube's ip:
```
minikube ip
```

## `kubectl`

Display cluster info
```
$ kubectl cluster-info
Kubernetes master is running at https://192.168.99.101:8443
KubeDNS is running at https://192.168.99.101:8443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy
```
