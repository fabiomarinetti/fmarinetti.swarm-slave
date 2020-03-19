[![Build Status](https://travis-ci.com/fabiomarinetti/fmarinetti.swarm-slave.svg?branch=master)](https://travis-ci.com/fabiomarinetti/fmarinetti.swarm-slave)

fmarinetti.swarm-slave
=========

Add a swarm worker to an existing cluster

Requirements
------------

None

Role Variables
--------------

- manager_ipaddress: the manager ip address **REQUIRED!!**
- manager_port: the port the manager listens on (default: 3277)
- token: the token for joining the swarm

Dependencies
------------

- fmarinetti.docker-secured

Example Playbook
----------------

Attach workers to an existing manager:
```
    - hosts: slaves
      vars: 
        manager_ipaddress: 10.10.1.2
      roles:
         - fmarinetti.swarm-slave
```

or you can pass the variable through command line:

```
ansible-playbook -i <inventory> -e --extra-vars '{"manager_ipaddress":"10.10.1.2"}' <playbook>
```
License
-------

BSD

Author Information
------------------
