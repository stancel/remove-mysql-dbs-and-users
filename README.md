remove_mysql_dbs_and_users
=========

Ansible role to remove one or more MySQL databases and users.

Requirements
------------

Must be using some compatible form of MySQL Server (MariaDB / MySQL / Percona)

Role Variables
--------------

(Required) Root password for MySQL Server
```
    remove_mysql_dbs_and_users_mysql_root_password: "Some secure root password"
```

Database to remove. Required unless "remove_mysql_dbs_and_users_use_list" is set to true.
```
    remove_mysql_dbs_and_users_db_name: "database-to-remove"
```

Database user to remove. Required unless "remove_mysql_dbs_and_users_use_list" is set to true.
```
    remove_mysql_dbs_and_users_db_user: "user-to-remove"
```

List of databases and users to setup. Not needed unless the "remove_mysql_dbs_and_users_use_list" variable is set to true. Default is false.
```
	remove_mysql_dbs_and_users_list_to_setup:
	  - {
		  name: 'my-db-to-create',
		  mysql_user: 'some-user'
		}
```
(Default) Will you be passing a list of databases and/or database users to remove?
```
    remove_mysql_dbs_and_users_use_list: false
```


Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

	- hosts: your_server
	  vars_files:
	    - vars/main.yml
	  roles:
	    - stancel.remove_mysql_dbs_and_users 

or just pass the variables in the playbook

	- hosts: your_server 
	  vars:
		remove_mysql_dbs_and_users_mysql_root_password: "my-secure-password"
		remove_mysql_dbs_and_users_db_name: "my-awesome-db"
		remove_mysql_dbs_and_users_db_user: "my-db-user"
	  roles:
	    - stancel.remove_mysql_dbs_and_users


License
-------

GPLv3

Author Information
------------------

[Brad Stancel](https://github.com/stancel)

