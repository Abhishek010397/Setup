# Setup

## Usage

Add the system information gathered above into a file called hosts.ini. For example:

```bash
[master]
<masters_ip>

[node]
<nodes_ip>

[k3s-cluster:children]
master
node

```

Start provisioning of the cluster using the following command:

```bash
ansible-playbook site.yml -i inventory/hosts.ini
```

## Kubeconfig

To get access to your **Kubernetes** cluster just

```bash
scp debian@master_pi:~/kube/config ~/.kube/config
```
