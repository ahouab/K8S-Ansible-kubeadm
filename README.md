# K8S-Ansible-kubeadm
install from scratch a Kubernetes cluster on 3 VM using Ansible

To install a Kubernetes cluster from scratch on three virtual machines using Ansible, follow these key steps. This method assumes you have three VMs ready to go and that Ansible is installed on your control machine (or one of the VMs).

Overview:
Set up a basic Ansible inventory.
Prepare the VMs (disable swap, configure networking, etc.).
Install Kubernetes components.
Initialize the Kubernetes master node.
Join worker nodes to the master.
Prerequisites:
Three VMs with a Linux distribution like Ubuntu 22.04 or CentOS 7+.
Ansible installed on a control machine or one of the VMs.
SSH access configured between the control machine and the VMs.
