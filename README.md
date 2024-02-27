ECGALAXY microk8s
===============

Ansible role that installs [MicroK8s](https://microk8s.io/) and addons.

Requirements
------------

- Ubuntu 22.04 LTS, which is the only platform currently supported.
- [Snap](https://snapcraft.io/).

Role Variables
--------------

- `microk8s_version`: The version of microk8s to install.
- `microk8s_user`: The user on the target host who will be using microk8s. **(required)**
- `microk8s_addons`: A list of addons to be enabled. (default: `[]`)

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: all
      roles:
        - ecgalaxy.microk8s
      vars:
        microk8s_user: user1
        microk8s_addons:
          - ingress
          - metrics-server

License
-------

Copyright the European Union 2022.

Licensed under the EUPL-1.2 or later.

Author Information
------------------

ECGALAXY team.
