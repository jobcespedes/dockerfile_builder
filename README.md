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

```yaml
- hosts: all
  roles:
    - jobcespedes.dockerfile_builder
```

License
-------

MIT

Author Information
------------------

Job Céspedes Ortiz: jobcespedes@gmail.com
