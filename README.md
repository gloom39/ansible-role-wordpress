Role Name
=========

The role will install wordpress on Ubuntu 22.04

Requirements
------------

1. Make sure port 80 and 3306 is not used by other process or service. Apache and Mysql needs to use port 80 and 3306
2. Apache service is run by different user other than www-data which is defined in the variable. The user will be created. 


Role Variables
--------------
DB_PASSWORD: "wordpress database password"

MYSQL_SOCKET_PATH: /var/run/mysqld/mysqld.sock

DB_NAME: "wordpress database name"

DB_USER: "wordpress database username"

APACHE_USER: "apache user other than www-data"

APACHE_GROUP: "apache group other than www-data"

WP_ADMIN: "wordpress admin user"

WP_PASSWORD: "worpress admin password"

WP_TITLE: "wordpress blog title"

WP_EMAIL: "wordpress email"


Dependencies
------------
* Ansible >= 2.16
* Supported OS:
  * Ubuntu 22.04 (Jammy)

```bash
ansible-galaxy collection install community.mysql
```

Example Playbook
----------------
```
---
- name: wordpress
  hosts: 
  - servers
  roles:
  - gloom39.wordpress
  vars:
    DB_PASSWORD: wordpress123
    MYSQL_SOCKET_PATH: /var/run/mysqld/mysqld.sock
    DB_NAME: wordpress
    DB_USER: wordpress
    APACHE_USER: wordpress
    APACHE_GROUP: wordpress
    WP_ADMIN: admin
    WP_PASSWORD: wordpress123
    WP_TITLE: my site
    WP_EMAIL: admin@example.com
```
License
-------
BSD

Author Information
------------------
@gloom39
