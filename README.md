Description
===========

Host specific configuration is stored in `host_vars/` directory.

Configuration
=============

In order to run playbook make sure:
 * Ansible control host can login via ssh as `root` to all cluster nodes;
 * `host_vars/nodeX` files are updated accordingly;
 * `group_vars/all.yml` is updated accordingly;

Running playbook
================

Current playbook does not designed to run against specific host. It should be run agains all hosts in cluster.
```
ansible-playbook -i inventory site.yml
```

Cluster cheatsheet
==================

Cluster status:
```
crm status 
```

DRBD status:
```
drbdadm status
```

Evacuate specific node:
```
crm node standby nodeX
```

Bring node back to online:
```
crm node online nodeX
```
