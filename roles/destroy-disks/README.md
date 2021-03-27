Destroy
=========

Detach and destroy non boot disk from GCP instance.

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


* name: "disk name"

* instance_attached: "GCP instance name where disk is attached"

* zone: "zone"

* gcp_cred_kind: serviceaccount

* gcp_cred_file: "Credentials file"

Example Playbook
----------------
```
---
- hosts: localhost
  roles:
  - destroy-disks
```
License
-------

BSD
