# Virtualbox based machine for Magento 2 development
VirtualBox and Docker/Kubernetes based VM for Magento 2 development on Windows systems.

This one is in an early stage of d e v e l o p m e n t.

## Prerequisities

### Install `kubectl` and `minikube`
1. `kubectl`. Follow https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-on-windows
2. `minikube`. Follow https://kubernetes.io/docs/tasks/tools/install-minikube/

## Booting up the environment
Start Minikube and create a cluster:
```
minikube start
```

## Notes
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

## Troubleshooting
#### Failed to open/create the internal network 'HostInterfaceNetworking-VirtualBox Host-Only Ethernet Adapter #3' (VERR_INTNET_FLT_IF_NOT_FOUND). 
```
C:\{in a galaxy far, far away}>minikube start
* minikube v1.4.0 on Microsoft Windows 10 Pro 10.0.18362 Build 18362
* Creating virtualbox VM (CPUs=2, Memory=2000MB, Disk=20000MB) ...
* Retriable failure: create: creating: Unable to start the VM: C:\Program Files\Oracle\VirtualBox\VBoxManage.exe startvm minikube --type headless failed:
VBoxManage.exe: error: Failed to open/create the internal network 'HostInterfaceNetworking-VirtualBox Host-Only Ethernet Adapter #3' (VERR_INTNET_FLT_IF_NOT_FOUND).
VBoxManage.exe: error: Failed to attach the network LUN (VERR_INTNET_FLT_IF_NOT_FOUND)
VBoxManage.exe: error: Details: code E_FAIL (0x80004005), component ConsoleWrap, interface IConsole

Details: 00:00:01.258526 Power up failed (vrc=VERR_INTNET_FLT_IF_NOT_FOUND, rc=E_FAIL (0X80004005))
* Deleting "minikube" in virtualbox ...
* Creating virtualbox VM (CPUs=2, Memory=2000MB, Disk=20000MB) ...
* Retriable failure: create: creating: Unable to start the VM: C:\Program Files\Oracle\VirtualBox\VBoxManage.exe startvm minikube --type headless failed:
VBoxManage.exe: error: Failed to open/create the internal network 'HostInterfaceNetworking-VirtualBox Host-Only Ethernet Adapter #3' (VERR_INTNET_FLT_IF_NOT_FOUND).
VBoxManage.exe: error: Failed to attach the network LUN (VERR_INTNET_FLT_IF_NOT_FOUND)
VBoxManage.exe: error: Details: code E_FAIL (0x80004005), component ConsoleWrap, interface IConsole
...
```
A solution: https://www.howtoforge.com/setup-a-local-wordpress-development-environment-with-vagrant/#note-for-windows-users 

For the records, the idea is to update network adapter's driver.

## Links
https://kubernetes.io/docs/setup/learning-environment/minikube/

## License
Copyright (c) We Are Interactive under the MIT license.
