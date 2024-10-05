# K8S-Ansible-kubeadm
Install from scratch a Kubernetes cluster on 3 VM using Ansible

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


Assign right IPs

Run the setup playbook to prepare all VMs:

ansible-playbook -i inventory.ini k8s-setup.yml

Then, run the master node initialization playbook:

ansible-playbook -i inventory.ini k8s-master.yml

Finally, run the playbook to join the worker nodes:

ansible-playbook -i inventory.ini join-workers.yml

Verify the Cluster:
After the worker nodes have joined, you can verify the cluster setup by SSHing into the master node and running:

kubectl get nodes


*******************
In case of repository debian problem

Do this:

sudo apt update
sudo apt install apt-transport-https curl

curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -


Create a new file in the /etc/apt/sources.list.d/ directory:

echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list



















