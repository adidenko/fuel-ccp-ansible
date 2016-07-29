fuel-ccp-ansible
================

Ansible playbooks to deploy Fuel-CCP.

Requirements
------------

* Kubernetes deployed with Kargo, this playbooks reuiqre kargo's inventoty

How to
------

* Default deployment:

```bash
export INVENTORY=/root/kargo/inventory/inventory.cfg
ansible-playbook -i /root/mcp/nodes_to_inv.py build.yaml
ansible-playbook -i /root/mcp/nodes_to_inv.py deploy.yaml
```

* Deploying networking-calico OpenStack neutron plugin instead of OVS:

```bash
export INVENTORY=/root/kargo/inventory/inventory.cfg
cat examples/calico.yaml
ansible-playbook -i /root/mcp/nodes_to_inv.py build.yaml -e @examples/calico.yaml
ansible-playbook -i /root/mcp/nodes_to_inv.py deploy.yaml -e @examples/calico.yaml
```
