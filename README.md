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

During execution, the `microk8s` group is created and the specified `microk8s_user` added to it.

This user may need to logout and login to be able to use the `microk8s` command.

Another way for the user is to execute `newgrp microk8s` in the terminal.

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

One-liner
---------

    bash <(curl -s https://code.europa.eu/-/snippets/1/raw/main/ansible-role.sh) ecgalaxy.microk8s --extra-vars '{"microk8s_user":"the_username_here"}'

See [ansible-role](https://code.europa.eu/-/snippets/1) for instructions.

Please verify the script integrity first.

License
-------

Copyright the European Union 2022.

Licensed under the EUPL-1.2 or later.

Author Information
------------------

ECGALAXY team.
