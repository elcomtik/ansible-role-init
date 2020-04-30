ansible-role-init
=========

Initial configuration of host to prepare for Ansible. Will ensure python is latest version, add user for ansible, give sudo presmisions and upload ssh_key for him. 

Requirements
------------

User on remote host which run playbook must have root privileges

Role Variables
--------------

Defaults:\
\
bootstrap_user: "root"\				#user which will initialy configure host, until ansible_user is created
\
remove_bootstrap_user_ssh_keys: false		#enables to delete ssh_key from bootstrap user account
\
ssh_user: ansible\
\
ssh_keys_path: "files/ssh-keys"			#path relative to playbook directory
\
ssh_keys: [] 					#by default empty list. Must be defined, should by name of pubkey file, which is placed in ssh_key_path directory\

Dependencies
------------

none

Example Playbook
---------------- 

	- hosts: all
	  gather_facts: no
	  roles:
	    - elcomtik.init

License
-------

MIT                                                                                                                                          

Author Information
------------------

mail@romandanko.sk, www.romandanko.sk
