AWS CLI Role
=========

This role will install the linux version of the aws_cli.   This will attempt to pull the latest version and install it.  It also is idempotence so it checks if the aws cli is already installed and will not change anything.   If you want this to replace an existing you'll need to manually remove the old version.  To do this delete

```bash
sudo rm -rf /usr/local/aws-cli
sudo rm /usr/local/bin/aws
sudo rm /usr/local/bin/aws_completer
sudo rm /bin/aws
```

Requirements
------------

- Ansible must be installed.
- AWS CLI must not be installed.

Role Variables
--------------

None

Dependencies
------------

None

Example Playbook
----------------

Using ansible-galaxy:

```bash
ansible-galaxy install devkingdom.aws-cli-role
```

---
```bash
- name install aws_cli
  hosts: all
  connection: local
  become: yes
  gather_facts: no
  roles:
    - role: devkingdom.aws-cli-role
```

Using git:

```bash
$ git clone git@github.com:devkingdom/aws-cli-role.git
```


License
-------

Apache-2.0

Author Information
------------------

Created by Stephen Paulin.   
[medium@spextreme](https://medium.com/@spextreme)

