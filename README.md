asnible-selinux-role
=========

This role installs necessary packages to allow Ansible performing SeLinux operations and set SeLinux to desired state. In case SeLinux state is changed server is rebooted

Requirements
------------

There is not any prerequisities for this role

Role Variables
--------------

    selinux_packages:
    - "policycoreutils-python"

Required package to allow Ansible performing SeLinux operations

    selinux_policy: "targeted"
    selinux_state: "enforcing"

Desired SeLinux state. Default policy is `targeted` and default state is `enforcing`

Dependencies
------------

There is not any dependencies

Example Playbook
----------------

Set SeLinux to default desired state - `targeted enforcing`

    - hosts: all
      roles:
         - "asnible-selinux-role"

Set SeLinux to another desired using overriding role variables

    - hosts: all
      roles:
        - role: "ansible-selinux-role"
          selinux_policy: "targeted"
          selinux_state: "disabled"

License
-------

BSD

Author Information
------------------

Jakub Slatinsky, slatinskyj@gmail.com
