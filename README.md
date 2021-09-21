Role Name
=========

This role is used to validate that prerequisites have been met that will allow for a successful installation of OpenShift 4.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

This roles was written and tested against Ansible 2.10.  

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Currently, the following variables are exposed.

domain: example.com # the domain.name your openshift environment will be installed in

cluster: ocp # the subdomain your openshift environment will be install - this will combine with the domain to create your FQDNS, eg api.ocp.example.com

reg_user: user # username for your openshift mirror registry, if doing an offline installation

reg_pass: pass # password for your openshift mirror registry, if doing an offline isntallation

reg_addr: registry.example.com:5000 # your mirrored docker registry fdqn + port number

image_path: /ocp4/openshift4 # The path where mirrored images are stored in your registr


Example Playbook
----------------

---
- hosts: localhost
  gather_facts: no
  connection: local
  roles:
  - ocp-poc-prereqs

This role can be called by a [python script](https://github.com/jritenour/ocp-poc-wrapper) which will gather variable input and run a [containerized version](https://hub.docker.com/repository/docker/jmritenour/ansible-ocp-poc) of this playbook to avoid dependency issues.  

License
-------

MIT

Author Information
------------------

JRit.  
