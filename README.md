mysql-server
============

An ansible role for the installation of MySQL on CentOS, Redhat, Debian and Amazon machine.

Requirements
------------

Python must be installed on remote server

Role Variables
--------------

```
mysql_root_password: "sandeep" # --> Defaults/main.yml

database_name: # --> vars/main.yml
        - { db_name: test1, db_user: sandeep, user_password: admin, user_access: '*.*:ALL' }
        - { db_name: test2, db_user: sanny, user_password: admin, user_access: '*.*:ALL' }
        - { db_name: test3, db_user: sandy, user_password: admin, user_access: '*.*:ALL' }
        - { db_name: test4, db_user: sny, user_password: admin, user_access: '*.*:ALL' }


```

Dependencies
------------

None

Example Playbook
----------------

A playbook to use the role.

```
---
  - hosts: hostgroup/host
    become: true
    roles: 
      - mysql_role
```

Author Information
------------------

```
Name: Sandeep Kumar Verma
Email: sandeep.verma@opstree.com
```
