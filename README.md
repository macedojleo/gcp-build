:heavy_check_mark: Requirements
------------

* ansible >= 2.9
* python >= 2.6
* requests >= 2.18.4
* google-auth >= 1.3.0
* gcp and service account


:pencil: GCP Variables
--------------

#### :closed_lock_with_key: Generate GCP project key File

``` $ gcloud iam service-accounts keys create key-file --iam-account=sa-name@project-id.iam.gserviceaccount.com ```

* key-file: The name of the private key file.
* sa-name: The name of the service account to create a key for.
* project-id: Your Google Cloud project ID.

#### :bulb: Another useful commands 

|     Value    | GCP Command |   Comments   |
|    :---:     |     :---:   |     :---:    |
| machine types| ``` $ gcloud compute machine-types list --filter="zone: your_zone" ```  | List all machine types available filtered by zone| 
| GCP Zone     | ``` $ gcloud compute regions list ``` | List all zones available  |
| Region       | ``` $ gcloud compute zones list ```  | List all regions available |


:rocket: Build GCP instance 
----------------
1. Fill out all required variables in the role/build-instance/vars/mail.yml file.
2. Run build playbook

```$ ansible-playbook build-instance.yml```


:warning: Destroy GCP instance 
----------------
1. Fill out all required variables in the role/destroy-instance/vars/mail.yml file. 
2. Run destroy playbook

```$ ansible-playbook destroy-instance.yml```

:floppy_disk: Create and attach new disk on GCP instance 
----------------
1. Fill out all required variables in the role/create-disks/vars/mail.yml file.
2. Run create-disk playbook

```$ ansible-playbook create-disk.yml```


:warning: Detach and destroy disk from GCP instance
----------------
1. Fill out all required variables in the role/destroy-disks/vars/mail.yml file. 
2. Run destroy-disk playbook

```$ ansible-playbook destroy-disk.yml```

:notebook: Dynamic Inventory
----------------
Using inventory.yml file as dynamic inventory you can list all GCP instances and create groups based on its tags.

1. Change both values into inventory.yml file: **project_name** and **credentials_file** 

2. Run the command below lists to list all your inventory:

```$ ansible-inventory -i inventory.yml --list```

3. You can view the populated inventory with:

```
$ ansible-inventory -i inventory.yml --graph

@all:
  |--@Porto:
  |  |--34.0.0.1
  |  |--34.0.0.2
  |--@Lisbon:
  |  |--35.0.0.1
  |--@ungrouped:
  |--@zone_us_central1_a:
  |  |--34.0.0.1
  |  |--34.0.0.2
  |  |--35.0.0.1
  
  ```
