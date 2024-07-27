Vector-role
=========
It is intended for installation on operating systems running the Vector service SystemD and basic configuration of tracking changes to LOG files with sending changes to Clickhouse

Variables
----------
- **vector_version** - The version of the Vector software used. By default 0.28.0

- **vector_test_dir**- is the directory for tracking LOG files.

- **clickhouse_host:** - Clickhouse host for uploading metrics.

- **clickhosue_port:** - Clickhouse port for uploading metrics.

- **clickhosue_user:** - A Clickhouse user with write permissions.

- **clickhosue_password:** - Password of the authorized Clickhouse user.

Usage example
--------------------
```yaml
- name: Install and configure Vector
  hosts: vector
  become: true
  vars:
    vector_test_dir: "/var/log/test"
    clickhouse_host: hostvars['clickhouse']['ansible_host']
  roles:
    - vector_role
```
