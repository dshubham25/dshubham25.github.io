---
layout: post
title: Openstack
category: Developer Environment
excerpt: Guide on hosting a Jekyll site with custom domain on Github Pages.
redirect_from: /2022/07/16/Openstack/
---

Openstack is an open-source software that provides cloud-infrastructure for the virtual machines, bare metals and containers.

<p>
<img src="https://www.freecodecamp.org/news/content/images/2022/04/openstack.svg", align="center">
</p>

Openstack is a cloud-computing platform that is used by the organisation to manage and control large scale deployements of virtual machines.

Openstack is 
- Scalable
- Reliable
- Provides Control

Openstack can also be used to manage storage and networking resources in a cloud environment.

| Openstack | AWS |
| --------| ---------|
| Open source| proprietary |
| more flexible | less flexible |
| harder setup | easier setup |

Openstack is broken up into services to basically plug and play components depending on the needs.

<p>
<img src="https://object-storage-ca-ymq-1.vexxhost.net/swift/v1/6e4619c416ff4bd19e1c087f27a43eea/www-assets-prod/openstack-map/openstack-map-v20210201.svg" align="center">
</p>

1. Openstack object storage(Swift): highly scalable distributed object storage system.
2. Openstack block storage(Cinder): Is a service for managing block storage devices.
3. Openstack compute(Nova): Is a cloud computing fabric controller which manages the allocation of compute resources.
4. Openstack networking(Neutron): Is a system for managing networks and IP Addresses.
5. Openstack dashboard(Horizon): Is a web-based interface for managing openstack resources.
6. Openstack identity(Keystone): Is a system for managing user accounts and access control.
7. Openstack image(Glance): Is a service for storing and retrieving virtual machine images.
8. Openstack bare metal(Ironic): Is a service for provisioning and managaing bare metal servers.

**Easiest way** to get started with Openstack is by using the *openmetal on-demand private cloud*.

- After creating an account on openmetal on-demand private cloud, you need to have an public ssh key which you get my typing on your systems cli

> ssh-keygen

It will generate a public/private key.
To access the private key
```
cd .ssh

ls

```
you will see some files mainly
- id_rsa.pem
- id_rsa.pub
- known_hosts

get access to the id_rsa.pub and copy and paste it into the prompt of the openmetal.

Openmetal gives a user access to openstack servers by providing it through ceph. Ceph is an open source software defined storage solution.