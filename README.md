# kubernetes-ansible-playbook
Ansible-playbook to deployment kubernetes via vagrant

# Package version
- Ubuntu 16.04
- kubeadm 1.9.1
- vagrant 2.0.1
- virtualbox 5.2.2 r119230
- ansible v2.4.2.0

# Install
ansible-playbook -i hosts.yml deploy-all.yml -e @vars.yml
