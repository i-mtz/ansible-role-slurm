Role Name
=========

Configure a SLURM cluster in a tenant

This role will configure:
  * slurm accounting daemon
  * slurm master daemon
  * slurm worker nodes
  * slurm submit hosts

Slurm users are automatically added to the slurm accounting db on the first job submission using 
a [lua job submission plugin](templates/job_submit.lua.j2)

Role Variables
--------------

```
slurm_update_etc_hosts_file: true  # add all the slurm hosts to /etc/hosts in every machine

slurm_master_host: slurm-master.cluster.com  # set this var to the ansible_hostname of the slurm-master
slurm_dbd_host: "{{ slurm_master_host }}"  # set this var to the ansible_hostname of the slurm-dbd host (slurm-master by default)

slurm_workers_group: slurm_workers  # group in your ansible inventory including all the slurm workers

slurm_submit_group: slurm_submit_hosts  # group in your ansible inventory including all the submit hosts

slurm_slurmdbd_mysql_db_name: slurm
slurm_slurmdbd_mysql_user: slurm
slurm_slurmdbd_mysql_password: aadAD432saAdfaoiu
```
