ansible-role-init
=========

Initial configuration of host to prepare for Ansible. Will ensure python is latest version, add user for ansible, give sudo presmisions and upload ssh_key for him. 

Requirements
------------

User on remote host which run playbook must have root privileges

Role Variables
--------------

Defaults:\
ssh_user: ansible\
\
ssh_keys_path: "/files/ssh-keys"	#path relative to playbook rundir
\
ssh_keys: [] 		#by default empty list. Must be defined, should by name of pubkey file, which is placed in ssh_key_path directory\

Dependencies
------------

none

Example Playbook
---------------- 

	- hosts: all
	  remote_user: root
	
	  pre_tasks:
	  - name: Override variables
	    set_fact:
	      ansible_user: 'root' 
	
	  roles:
	    - ansible-role-init

License
-------

"THE BEERWARE LICENSE" (Revision 42):                                                                                                                                            
                                                                                                                                                                                 Roman Danko wrote this code. As long as you retain this notice, you can do whatever you want with this stuff. If we meet someday, and you think this stuff is worth it, you can buy me a beer in return.

Author Information
------------------

roman.danko@ynet.sk, Ynet, Staré Grunty 53,841 04 Bratislava 4, Slovakia, www.ynet.sk
