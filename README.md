# Basic Ansible ha-proxy role

Simple ha-proxy role to install and setup ha-proxy. 

I am using this role to setup ha-proxy as loadbalancer for Kubernetes Ingress controllers.

Currently the role suppports only debian-based distributions. 

## Concept

The ha-proxy is used as a load-balancer. It distributes incoming traffic (http/80 and https/443) to a list of Kubernetes Nodes (http/31080 and https/31443).

Kubernetes is running nginx Ingress controller as NodePort-Service on ports _31080_ and _31433_.


## Role Variables

Only the hosts of group _[vpn]_ are used. Currently no other variables are supported.

The ha-proxy distributes load to all hosts of group _[vpn]_. 