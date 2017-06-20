Stouts.rabbitmq
===============

[![Build Status](http://img.shields.io/travis/Stouts/Stouts.rabbitmq.svg?style=flat-square)](https://travis-ci.org/Stouts/Stouts.rabbitmq)
[![Galaxy](http://img.shields.io/badge/galaxy-Stouts.rabbitmq-blue.svg?style=flat-square)](https://galaxy.ansible.com/list#/roles/953)

Ansible role which manage RabbitMQ.

#### Variables

```yaml
rabbitmq_enabled: yes

rabbitmq_plugins:                       # Ensure the plugins is installed
  - rabbitmq_management

rabbitmq_users:                         # Ensure the users added
  - user: admin
    password: admin
    permissions:
      - vhost: /
        configure_priv: .*
        read_priv: .*
    tags: administrator

rabbitmq_vhosts: []                     # Ensure the vhosts are exists

rabbitmq_vhosts_node: rabbit@{{ansible_hostname}} # Name of the node to apply the vhosts

rabbitmq_users_remove:                  # Ensure the users removed
  - guest
```

#### Usage

Add `Stouts.rabbitmq` to your roles and set vars in your playbook file.

Example:

```yaml

- hosts: all

  roles:
    - Stouts.rabbitmq

  vars:
    rabbitmq_vhosts: [myhost]
```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.rabbitmq/issues)!
