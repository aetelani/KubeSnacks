# KubeSnacks
Kubernetes notes
# First steps
## Installing development environment
OS: Debian Jessie
* Update kernel
* Enable Virtualization BIOS extensions
* Install Docker
* Install VirtaulBox >4. VirtualBox by default, kvm works as well.
* Install GCloud sdk: Debian repo works fine
* install minikube: eg. deb package
## Commands
eval $(minikube docker-env); docker ps #Docker uses Kubernetes env
eval $(minikube docker-env -d); docker ps #kubernetes env disabled.
minikube {start, stop, delete}
## Problems
host-ip cidr reserved on re-start. Fix: reboot, or update ip virtualbox, minikube startup parameters, see related bug
