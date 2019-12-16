Role Name: dockerfile_builder
=========

[![Build Status](https://travis-ci.org/jobcespedes/dockerfile_builder.svg?branch=master)](https://travis-ci.org/jobcespedes/dockerfile_builder) [![Buy me a coffee](https://img.shields.io/badge/$-BuyMeACoffee-blue.svg)](https://www.buymeacoffee.com/jobcespedes)

Generate Dockerfiles and build image containers using Ansible

Requirements
------------

- See [`requirements.txt`](requirements.txt)

Role Variables
--------------

- See [`defaults/main.yml`](defaults/main.yml).

Dependencies
------------

- Depends on other Ansible roles: no

Example Playbook
----------------
Create a folder structure for your container(s). There should be at least a Dockerfile.j2 template there. The role will also copy a conf directory if present. The following is an example for multiple containers:
```bash
├── example.com
│   ├── mycontainer
│   │   ├── conf
│   │   │   └── myfile
│   │   └── Dockerfile.j2
│   └── mycontainer2
│       ├── conf
│       │   └── myfile2
│       └── Dockerfile.j2
├── playbook.yml

```

```yaml
- hosts: all
  vars:
    mycontainers:
      - example.com/mycontainer
      - example.com/mycontainer2
  tasks:
    - name: include builder role
      loop: "{{ mycontainers }}"
      vars:
        dockerfile_builder_image: "{{ item }}"
      include_role:
        name: jobcespedes.dockerfile_builder
```

License
-------

MIT

Author Information
------------------

Job Céspedes Ortiz: jobcespedes@gmail.com
