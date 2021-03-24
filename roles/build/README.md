Build
=========

Create an Virtual Machine instance on GCP (Google Cloud Platform)

Requirements
------------

* ansible >= 2.9
* python >= 2.6
* requests >= 2.18.4
* google-auth >= 1.3.0
* service account and gcp account

Role Variables
--------------

### Put here details regarding your GCP project info and credentials.    

* gcp_project: "Project name"

* gcp_cred_kind: serviceaccount

* gcp_cred_file: "Credential file"


### Put here details regarding your new instance.

* gcp_mach_type: "machine type"

* zone: "GCP Zone"

* region: "GCP Region"

* image: 'Compute engine'

* resource:
       
       name: "Instance Name"
       
       disk: -- "Disk Name" 
       
       size: -- "Disk size, e.g 10 means 10Gb"
       
       address: -- "Resource address name"

Dependencies
------------

N/A

Example Playbook
----------------

```
---
- hosts: localhost
  roles:
  - build
```

License
-------

BSD
