# 🔧 Ansible Inside Kubernetes

This project demonstrates how to run Ansible commands and playbooks from one pod (`ansible-pod`) to configure another (`target-pod`) inside a Kubernetes cluster.

## ✅ Components

- `ansible-pod/` - Dockerfile and YAML to build the Ansible pod
- `target-pod/` - Ubuntu-based pod with SSH enabled
- `ansible/` - Contains the Ansible inventory file and playbook

## ⚙️ Steps

1. Build and push Docker image for ansible-pod
2. Deploy both pods with kubectl
3. SSH from Ansible pod to Target pod
4. Configure `/etc/ansible/hosts`
5. Run ad-hoc Ansible commands and playbooks

## 🧪 Sample Output

```bash
ansible all -i /etc/ansible/hosts -m ping

10.244.0.6 | SUCCESS => {
    "ping": "pong"
}
