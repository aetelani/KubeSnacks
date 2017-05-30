# KubeSnacks
Kubernetes notes
# First steps
## Installing development environment
OS: Debian Jessie
* Update kernel
* Enable Virtualization BIOS extensions
* Install Docker
* Install VirtaulBox >4. VirtualBox by default, kvm works as well.
* Install GCloud sdk: Debian repo works fine <sup>1</sup>
* Install kubectl: ```sudo apt install kubectl```
* install minikube: eg. deb package <sup>2</sup>

1: https://cloud.google.com/sdk/docs/quickstart-debian-ubuntu</br>
2: https://github.com/kubernetes/minikube/releases
## Commands
```
eval $(minikube docker-env); docker ps #Docker uses Kubernetes env
eval $(minikube docker-env -d); docker ps #kubernetes env disabled.
minikube {start, stop, delete}
```
## Problems
host-ip cidr reserved on re-start. Fix: reboot, or update ip virtualbox, minikube startup parameters, see related bug
