Role Name
=========

This role will install docker-compose on targeted remore hosts, both redhat-based and debian-based.
It has two main directories with main yaml files:

	- tasks/main.yaml
	- defaults/main.yaml

Requirements
------------

Nothing.

Role Variables
--------------

Docker Compose options.

docker_install_compose: true

docker_compose_version: "2.2.3"

docker_compose_arch: x86_64

docker_compose_url: "https://github.com/docker/compose/releases/download/v{{ docker_compose_version }}/docker-compose-Linux-{{ docker_compose_arch }}"

docker_compose_path: /usr/local/bin/docker-compose

Dependencies
------------

Nothing.

How to execute 
----------------

Normal installation : ansible-playbook -i inventory.ini -b install-docker-compose.yaml

force installation : ansible-playbook -i inventory.ini -b install-docker-compose.yaml --skip-tags "Exit"

License
-------

BSD

Author Information
------------------

By Saeed yasrebi.
