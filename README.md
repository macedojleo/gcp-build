:memo: Requirements
------------

* ansible >= 2.9
* python >= 2.6
* requests >= 2.18.4
* google-auth >= 1.3.0
* gcp and service account


GCP Variables
--------------

### Run the following **gcloud** command in order to create GCP credentials:

``` $ gcloud iam service-accounts keys create key-file --iam-account=sa-name@project-id.iam.gserviceaccount.com ```

* key-file: The name of the private key file.
* sa-name: The name of the service account to create a key for.
* project-id: Your Google Cloud project ID.

### Another useful GCP commands 

|     Value    | GCP Command |   Comments   |
|    :---:     |     :---:   |     :---:    |
| machine types| ``` $ gcloud compute machine-types list --filter="zone: your_zone" ```  | List all machine types available filtered by zone| 
| GCP Zone     | ``` $ gcloud compute regions list ``` | List all zones available  |
| Region       | ``` $ gcloud compute zones list ```  | List all regions available |


Build GCP instance 
----------------
1. Put all required information into the variable role/build-instance/vars/mail.yml file.
2. Run build playbook

```$ ansible-playbook build-instance.yml```


Destroy GCP instance 
----------------
1. Put all required information into the variable role/destroy-instance/vars/mail.yml file. 
2. Run destroy playbook

```$ ansible-playbook destroy-instance.yml```

Create and attach new disk on GCP instance 
----------------
1. Put all required information into the variable role/create-disks/vars/mail.yml file.
2. Run create-disk playbook

```$ ansible-playbook create-disk.yml```


Detach and destroy disk from GCP instance
----------------
1. Put all required information into the variable role/destroy-disks/vars/mail.yml file. 
2. Run destroy-disk playbook

```$ ansible-playbook destroy-disk.yml```

Dynamic Inventory
----------------
Use inventory.yml file as dynamic inventory in order to list all hosts and groups.

1. Change both values into inventory.yml file: **project_name** and **cresentials_file** 

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
