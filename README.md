k8s-kubeadm-containerd-role
=========

An ansible role for installing k8s based on cri containerd via kubeadm on Linux CentOS8.

Requirements
------------

- A compatible Linux host. The Kubernetes project provides generic instructions for Linux distributions based on Debian and Red Hat, and those distributions without a package manager.
- 2 GB or more of RAM per machine (any less will leave little room for your apps).
- 2 CPUs or more.
- Full network connectivity between all machines in the cluster (public or private network is fine).
- Unique hostname, MAC address, and product_uuid for every node.
- Certain ports are open on your machines

[Source kubernetes.io](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/)

Role Variables
--------------

### Vars for kubeadm config file  generated to /tmp/configkube.yaml
### For test purposes just change "ipv4_master" and "hostname" var
ipv4_master: 192.168.0.30
dnscluster: cluster.local
service_subnet: 10.96.0.0/12
hostname: cent30

### Additional vars for disable firewalld - when false just create rule for ports: 6443,2379-2380,10250,10251,10252
disable_firewall: true


### Vars for repository settings
kubernetes_yum_base_url: "https://packages.cloud.google.com/yum/repos/kubernetes-el7-$basearch"
kubernetes_yum_gpg_key:
  - https://packages.cloud.google.com/yum/doc/yum-key.gpg
  - https://packages.cloud.google.com/yum/doc/rpm-package-key.gpg

docker_baseurl: https://download.docker.com/linux/centos/$releasever/$basearch/stable
docker_gpg_key: https://download.docker.com/linux/centos/gpg

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
