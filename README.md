ansible-role-ha-proxy
=====

Simple ha-proxy role to install and setup ha-proxy. 

I am using this role to setup ha-proxy as loadbalancer for Kubernetes Ingress controllers.

The ha-proxy is used as a load-balancer. It distributes incoming traffic (http/80 and https/443) to a list of Kubernetes Nodes (http/31080 and https/31443).

Kubernetes is running nginx Ingress controller as NodePort-Service on ports _31080_ and _31433_.

Currently the role suppports only debian-based distributions. 

Requirements
----
This role was created for Debian based linux distributions.

Role Variables
----

The hosts of group _[vpn]_ are used. 

The ha-proxy distributes load to all hosts of group _[vpn]_ by the default port 31443 is used for ssl and 31080 for non-ssl traffic.


Example Playbook
----
This role can be easily used in a playbook like this: 

```yaml
- hosts: all
  roles:
      - ansible-role-ha-proxy
```

License
-------
GNU GENERAL PUBLIC LICENSE VERSION 3

Author Information
------------------
[blog.retter.jetzt](https://blog.retter.jetzt)


