ansible-role-init
=========

Initial configuration of host to prepare for Ansible 

Requirements
------------


Role Variables
--------------

ssh_user: ansible 	#by default ansible. Set it if you need\
\
ssh_keys_path: "/files/ssh-keys"	#by default /files/ssh-keys\
\
ssh_keys: 		#by default empty. Must be defined, should by path or url of pubkey file. also can by list of multiple keys\

Dependencies
------------


Example Playbook
----------------

This role is specific, because we sugest that host is not yet capable of Ansible managment(missing python, libs, priviledged accounts, ...). So we use very limited ansible features, to cope with this environment and hopefully setup this features with this role. :

	- hosts: all
	  remote_user: root
	  become: no
	  gather_facts: False
	
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
