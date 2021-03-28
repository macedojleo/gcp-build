create-disks
=========

create and attach disk on GCP instance (Google Cloud Platform)

Requirements
------------

* ansible >= 2.9
* python >= 2.6
* requests >= 2.18.4
* google-auth >= 1.3.0
* service account and gcp account

Role Variables
--------------

### Put here informations regarding the VM will be destroyed

* gcp_project: "Project name"

* gcp_cred_kind: serviceaccount

* gcp_cred_file: "Credentials file"

* zone: "zone"

* name: "disk name"

* disk_size: "size in Gb"

* disk_type: "pd-standard, pd-balanced, or pd-ssd"

* instance_to_attach: "GCP Instance to attach disk" 

Example Playbook
----------------
```
---
- hosts: localhost
  roles:
  - create-disk
```
License
-------

BSD
