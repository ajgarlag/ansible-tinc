ajgarlag.tinc
=============

Ansible role to setup a VPN with tinc.

[![Build Status](https://travis-ci.org/ajgarlag/ansible-tinc.svg?branch=master)](https://travis-ci.org/ajgarlag/ansible-tinc)

Role Variables
--------------

* **ajgarlag_tinc_network**: Name of the network (defaults to `myvpn`).
* **ajgarlag_tinc_network_autostart**: Boolean flag to autostart the VPN while booting (defaults to `true`).
* **ajgarlag_tinc_network_directives**: Dictionary of directives for tinc.conf (defaults to `{Name: '{{ ajgarlag_tinc_node_name }}', AddressFamily: 'ipv4'}`).
* **ajgarlag_tinc_network_nodes_group**: Group of tinc nodes to collect host files from (defaults to `all`).
* **ajgarlag_tinc_node_public_address**: Public IP address of the tinc node (defaults to '`{{ ansible_eth0.ipv4.address }}`').
* **ajgarlag_tinc_node_name**: Name of the tinc node.
* **ajgarlag_tinc_node_address**: Private IP address of the tinc node.
* **ajgarlag_tinc_node_directives**: Dictionary of directives of the tinc node for the host file (defaults to `{}`).
* **ajgarlag_tinc_node_up_script**: Source of the tinc-up script (see [defaults](defaults/main.yml)).
* **ajgarlag_tinc_node_down_script**: Source of the tinc-down (see [defaults](defaults/main.yml)).
* **ajgarlag_tinc_road_warriors**: Dictionary of road warriors configurations (defaults to `{}`).

Example Playbook
----------------

```yml
- hosts: all
  roles:
    - role: ajgarlag.tinc
      ajgarlag_tinc_network: extranet
```

License
-------

MIT

Author Information
------------------

Developed with ♥ by [Antonio J. García Lagar](http://aj.garcialagar.es).
