Role Name
=========

This role will install docker-ce on targeted remore hosts, both redhat-based and debian-based.
It has four main directories with main yaml files:

    - tasks
        - main.yaml
        - redhat.yaml
        - debian.yaml
    - defaults
        - main.yaml
    - vars
        - main.yaml
    - handlesrs
        - main.yaml

Requirements
------------
Nothing.

Role Variables
--------------

There are two types of variables:
- defaults/main.yml
 
  Edition can be one of: 'ce' (Community Edition) or 'ee' (Enterprise Edition).   
  
    - docker_edition: 'ce'
    - docker_package: "docker-{{ docker_edition }}"
    - docker_package_state: present

  Docker repo URL.
    
    - docker_repo_url: https://download.docker.com/linux

  GPG keyring local path
    
    - gpg_keyring_local_path: /usr/share/keyrings

  Used only for Debian/Ubuntu. Switch 'stable' to 'nightly' if needed.
    
    - docker_apt_release_channel: stable
    - docker_apt_arch: amd64
    - docker_apt_source_list: /etc/apt/sources.list.d/docker.list

  Used only for RedHat/CentOS/Fedora.
    
    - docker_yum_repo_url: "{{ docker_repo_url }}/{{ (ansible_distribution == 'Fedora') | ternary('fedora','centos') }}/docker-{{ docker_edition }}.repo"
    - docker_yum_repo_enable_nightly: '0'
    - docker_yum_repo_enable_test: '0'
    - docker_yum_gpg_key: "{{ docker_repo_url }}/centos/gpg"

  Service options.
    
    - docker_service_state: started
    - docker_service_enabled: true
    - docker_restart_handler_state: restarted

- vars/main.yml
  dependencies:
  
    - apt-transport-https
    - ca-certificates
    - curl
    - gnupg
    - lsb-release
  

Dependencies
------------

Nothing.

How to execute the playbook?
----------------

ansible-playbook -i inventory.ini -b install-docker.yaml

    -b : will running all plays as root user.
    
ansible-playbook -i inventory.ini -b install-docker.yaml --skip-tags "exit from role"

    It will forcing docker installation or update.
    

License
-------

BSD

Author Information
------------------

By Saeed Yasrebi.
