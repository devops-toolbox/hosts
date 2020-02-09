Role Name
=========

hosts

[![Build Status](https://travis-ci.org/cmihai-ansible/hosts.svg?branch=master)](https://travis-ci.org/cmihai-ansible/hosts)

Ansible galaxy:
---------------

[https://galaxy.ansible.com/devops-toolbox.hosts](https://galaxy.ansible.com/devops-toolbox.hosts)

```bash
ansible-galaxy install devops-toolbox.hosts
```

Requirements
------------

- For RHEL, a Red Hat subscription or functional local repository.

Role Variables
--------------

```yaml
hosts_remove_packages: true
hosts_enable_service: true
hosts_enable_selinux: true
hosts_firewall_configure: true
hosts_firewall_rules:
  - service:
```

Dependencies
------------

- For Red Hat, subscription-manager.

Example Playbook
----------------

```yaml
---
- name: Install hosts on localhost
  hosts:
    - localhost
  connection: local

  tasks:
    - name: hosts is configured
      import_role:
        name: devops-toolbox.hosts
      vars:
        hosts_remove_packages: true
        hosts_enable_service: true
        hosts_firewall_configure: true
        hosts_firewall_rules:
          - service:
      tags: hosts
```

License
-------

MIT

Author Information
------------------

- [Mihai Criveti](https://www.linkedin.com/in/devops-toolbox.)
