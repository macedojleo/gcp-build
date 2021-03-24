Requirements
------------

* ansible >= 2.9
* python >= 2.6
* requests >= 2.18.4
* google-auth >= 1.3.0
* service account and gcp account

Build GCP instance 
----------------
1. Put all information in role/build/vars/mail.yml file.
2. Run build playbook

```ansible-playbook run_build.yml```


Destroy GCP instance 
----------------
1. Put all information in role/destroy/vars/mail.yml file. 
2. Run destroy playbook

```ansible-playbook run_destroy.yml```
