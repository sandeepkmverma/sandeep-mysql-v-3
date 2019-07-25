mysql-server
============

An ansible role for the installation of MySQL on CentOS, Redhat, Debian and Amazon machine.

Requirements
------------

Python must be installed on remote server

Role Variables
--------------

```
# defaults/main.yml

mysql_root_password: "sandeep"
mysql_rpm_name: mysql-community-release-el6-5.noarch.rpm
zlib_tar_file: zlib-1.2.11.tar.gz

```

```
# vars/main.yml

debian_package_name:
        - { pkg_name: mysql-server }
        - { pkg_name: python-mysqldb }

mysql_repo: http://repo.mysql.com/{{mysql_rpm_name}}

debian_package_Python_MySQL:
        - { pkg_name: mysql-client }
        - { pkg_name: mysql-common }
        - { pkg_name: mysql-server }
        - { pkg_name: python-mysqldb }
        - { pkg_name: python3-dev }
        - { pkg_name: python3-mysqldb }
        - { pkg_name: libmysqlclient-dev }

centos_package_name:
        - { pkg_name: mysql }
        - { pkg_name: mysql-server }
        - { pkg_name: MySQL-python }
        - { pkg_name: libselinux-python }

zlib_package: https://zlib.net/{{zlib_tar_file}}


```

Dependencies
------------

None

Example Playbook
----------------

A playbook to use the role.

```

- hosts: hostgroup/host
  become: true
  roles:
    - mysql_role
    - mysql_database_and_users

```

Author Information
------------------

```
Name: Sandeep Kumar Verma
Email: sandeep.verma@opstree.com
```
