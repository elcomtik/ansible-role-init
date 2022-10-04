# ansible-role-init

[![Average time to resolve an issue](http://isitmaintained.com/badge/resolution/elcomtik/ansible-role-init.svg)](http://isitmaintained.com/project/elcomtik/ansible-role-init "Average time to resolve an issue")
[![Percentage of issues still open](http://isitmaintained.com/badge/open/elcomtik/ansible-role-init.svg)](http://isitmaintained.com/project/elcomtik/ansible-role-init "Percentage of issues still open")

Initial configuration of host to prepare for Ansible. 
Will ensure:
- python is latest version
- user for ansible is created with sudo presmisions
- ssh_key for ansible user is added
- sshd port is configured acording to inventory value of ansible_port

## Requirements

User on remote host which run playbook must have root privileges

## Role Variables

Defaults:

    # user which will initialy configure host, until ansible_user is created
    bootstrap_user: "root"

    # enables to delete ssh_key from bootstrap user account
    remove_bootstrap_user_ssh_keys: false

    # user which will be used by ansible
    ssh_user: ansible

    # path relative to playbook directory
    ssh_keys_path: "files/ssh-keys"

    # by default empty list. Must be defined, should by name of pubkey file, which is placed in ssh_key_path directory
    ssh_keys: []

    # ssh port which we want to set listening on
    ansible_port: 2222

    # enables to remove default(22) SSH listen port
    remove_default_ssh_port: false

## Dependencies

none

## Example Playbook

```yaml
  - hosts: all
    gather_facts: no
    roles:
      - elcomtik.init
```

## License

MIT                                                                                                                                          

## Author Information

mail@romandanko.sk, www.romandanko.sk
