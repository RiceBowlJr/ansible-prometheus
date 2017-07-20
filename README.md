Ansible-Prometheus
=========

Installs the Prometheus monitoring server and configure it to pull data from a NetData Master.
Role Variables
--------------

```yml
prometheus_version: 1.17.1
prometheus_root_dir: /opt/prometheus
# prometheus_config_dir: /etc/prometheus
prometheus_server_dir: "{{ prometheus_root_dir }}/prometheus-server"
prometheus_bin_dir: "{{ prometheus_root_dir }}/bin"
prometheus_dist_dir: "{{ prometheus_root_dir }}/dist"
prometheus_db_dir: "{{ prometheus_root_dir }}/databases"
prometheus_host_domain_name: yourdomain.org
```

Example Playbook Role Usage
----------------

## Simple setup

Install and run Prometheus and node_exporter using Upstart.

```yml
---
# This playbook deploys the whole application stack in this site.
 
- name: deploy prometheus on the prometheus nodes
  hosts: my-host
  remote_user: ubuntu
  become: yes 
  become_method: sudo
 
  roles:
      - ansible-prometheus
```

And execute it with:

```bash
ansible-playbook my-playbook.yml
```


License
-------

Apache v2.0

Author Information
------------------

Forked from the work of Grig Gheorghiu
http://agiletesting.blogspot.com
