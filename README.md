mamercad.mariadb-galera-haproxy-keepalived
==========================================

Stands up HA (keepalived) HAProxy in front of MariaDB Galera on RHEL/CentOS

Warnings
--------

The role puts SELinux into permissive mode and disabled firewalld

Requirements
------------

None

Role Variables
--------------

See the example inventory below, as well as vars/main.yml (basically, it spins
up a VIP, and haproxy listens on the VIP for TCP, redirecting round-robin to
each of the MariaDB nodes)

Dependencies
------------

None

Example Inventory
-----------------

    [marialb]
    marialb1
    marialb2

    [marialb:vars]
    ansible_ssh_user=root

Example Playbook
----------------

    - hosts:
        - marialb
      roles:
        - mariadb-galera-haproxy-keepalived

License
-------

GPLv3

Author Information
------------------

Mark Mercado <mamercad@umflint.edu>
