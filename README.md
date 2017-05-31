# KubeSnacks
Kubernetes notes
# First steps
Easy way to get things up and running.
## Installing development environment
OS: Debian Jessie Backports <sup>4</sup>
* Enable Backports: ```sudo deb http://ftp.debian.org/debian jessie-backports main contrib non-free #use closest mirror```
* Update packages: ```sudo apt update && sudo apt upgrade -y```
* Update kernel. Enable KVM if using kvm for virtualization.
* Enable Virtualization BIOS extensions
* Install Docker. (rkt is supported too but Docker is default): ```sudo apt install docker-ce #fresh from backports```
* Post docker install steps: ```sudo groupadd docker; sudo usermod -aG docker $USER; gnome-session-quit #logout```
* Install build essentials and headers: ```sudo apt install -y build-essential linux-headers-$(uname -r|sed 's,[^-]*-[^-]*-,,')```
* Install VirtualBox >4. VirtualBox by default, kvm works as well. ```sudo apt install -y virtualbox-5.1```
* Compile VirtualBox kernel additions: ```sudo /sbin/vboxconfig```
* Install GCloud sdk: Debian repo works fine <sup>1</sup>
* Install kubectl: ```sudo apt install kubectl```
* install minikube: eg. deb package <sup>2</sup>
## Commands cheat sheet
```
eval $(minikube docker-env); docker ps #Docker uses Kubernetes env
eval $(minikube docker-env -u); docker ps #kubernetes env unset.
minikube {start, stop, delete}
```
## Problems
host-only-cidr reserved on re-start. Fix: reboot, or update ip virtualbox, minikube startup parameters, see related bug <sup>3</sup>

---
1: https://cloud.google.com/sdk/docs/quickstart-debian-ubuntu</br>
2: https://github.com/kubernetes/minikube/releases</br>
3: https://github.com/kubernetes/minikube/issues/510</br>
4: https://backports.debian.org/</br>
