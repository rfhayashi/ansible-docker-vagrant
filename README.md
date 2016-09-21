Role Name
=========
Ansible Role that installs Docker Engine on CentOS in a way that is useful for Vagrant.

- Adds the vagrant user to docker group
- Sets docker to use a local registry. This is useful to cache docker images on the Vagrant host.

Requirements
------------

None.

Role Variables
--------------

    registry_address: localhost:5000 

Dependencies
------------

    - rfhayashi.docker

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: rfhayashi.docker-vagrant }

License
-------

MIT