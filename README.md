# kubernetes-ansible-playbook
Ansible-playbook to deployment kubernetes via vagrant

# Package version
- kubeadm 1.6.2
- vagrant 1.9.4
- virtualbox 5.1.22

# Install
ansible-playbook -i hosts deploy-all.yml -e @vars.yml
