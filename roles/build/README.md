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

* gcp_project: -- Your project name

* gcp_cred_kind: serviceaccount

* gcp_cred_file: -- Create credentials file by running ``` $ gcloud iam service-accounts keys create key-file --iam-account=sa-name@project-id.iam.gserviceaccount.com ```

		key-file: The path to a new output file for the private key.
	
		sa-name: The name of the service account to create a key for.
	
		project-id: Your Google Cloud project ID.  


### Put here details regarding your new instance.

* gcp_mach_type: "machine type" -- List all machine types available on GCP by running ``` $ gcloud compute machine-types list --filter="zone: your_zone" ```

* zone: "GCP Zone" -- List all zones by running ``` $ gcloud compute regions list ```

* region: "GCP Region" -- List all regions in a project in table form by running ``` $ gcloud compute zones list ```

* image: 'Compute engine' -- List all Google Compute Engine by running ``` $ gcloud compute images list ```

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
