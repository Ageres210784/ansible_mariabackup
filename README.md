ageres210784.ansible_mariabackup
=========

Role for mariabackup installation and configuration.

Requirements
------------

Ansible Galaxy

Role Variables
--------------

To run this role, you need to provide your Amazon s3 account information. For example:

```yaml
mariabackup_s3:
  region: region
  output: yaml
  aws_access_key_id: "aws_access_key_id"
  aws_secret_access_key: "aws_secret_access_key"
mariabackup_s3_backet: "backet_name"
mariabackup_s3_prefix: "some_prefix"
```

Restore
-------

To restore the database to the desired date, use the mariabackup_restore.sh script with the date in the format YYYY-MM-DD-hh-mm-ss or without "-". If you do not specify a date, the current date will be used. For example:

```bash
./mariabackup_restore.sh 2021-07-12-13-50-00
```

```bash
./mariabackup_restore.sh 20210712135000
```

```bash
./mariabackup_restore.sh
```

You can see all vars in `default/main.yml` vars file.

Dependencies
------------

None

Tested with Ansible
-------------------

    2.9

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - role: ageres210784.ansible_mariabackup
```

License
-------

Apache 2.0

Author Information
------------------

Evseev Sergey
