fuel-ccp-ansible
================

Ansible playbooks to deploy Fuel-CCP.


How to
------

* Make sure you have inventory.cfg, in the examples below we're using the same
inventory that was used for Kubernetes deployment with Kargo.

* Default deployment:

```bash
export INVENTORY=/root/kargo/inventory/inventory.cfg
ansible-playbook -i $INVENTORY build.yaml
ansible-playbook -i $INVENTORY deploy.yaml
```

* Deploying networking-calico OpenStack neutron plugin instead of OVS:

```bash
export INVENTORY=/root/kargo/inventory/inventory.cfg
cat examples/calico.yaml
ansible-playbook -i $INVENTORY build.yaml -e @examples/calico.yaml
ansible-playbook -i $INVENTORY deploy.yaml -e @examples/calico.yaml
```
