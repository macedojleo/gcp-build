Destroy
=========

Destroy an Virtual Machine instance on GCP (Google Cloud Platform)

Requirements
------------

ansible >= 2.9

python >= 2.6

requests >= 2.18.4

google-auth >= 1.3.0

service account and gcp account

Role Variables
--------------

### Put here informations regarding the VM will be destroyed

gcp_project: "Project name"

gcp_cred_kind: serviceaccount

gcp_cred_file: "Credentials file"

zone: "zone"

resource:
       
       name: "VM name"

Example Playbook
----------------
```
---
- hosts: localhost
  roles:
  - destroy
```
License
-------

BSD
