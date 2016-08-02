fuel-ccp-ansible
================

Ansible playbooks to deploy Fuel-CCP.


How to
------

* Make sure you have inventory.cfg, in the examples below we're using the same
inventory that was used for Kubernetes deployment with Kargo.

* Default deployment (on 3 Kubernetes worker nodes named: node1, node2, node3.
See examples for customization):

```bash
export INVENTORY=/root/kargo/inventory/inventory.cfg
ansible-playbook -i $INVENTORY build.yaml
ansible-playbook -i $INVENTORY deploy.yaml
```

* In order to run the same under sudo user (not root) you can do this

```bash
export INVENTORY=/root/kargo/inventory/inventory.cfg
ansible-playbook -i $INVENTORY build.yaml -b --become-user root
ansible-playbook -i $INVENTORY deploy.yaml -b --become-user root
```

* Deploying networking-calico OpenStack neutron plugin instead of OVS:

```bash
export INVENTORY=/root/kargo/inventory/inventory.cfg
cat examples/calico.yaml
ansible-playbook -i $INVENTORY build.yaml -e @examples/calico.yaml
ansible-playbook -i $INVENTORY deploy.yaml -e @examples/calico.yaml
```

Info
----

Check `examples/calico.yaml` example file for some basic options.

