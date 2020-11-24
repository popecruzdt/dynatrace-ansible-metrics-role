dynatrace-ansible-metrics-role
=========

This role enables you to send metrics about Ansible (Tower) job/playbook execution to Dynatrace.  Add the role as tasks within your playbook and specify the metric group and metric name as variables.  Use this to monitor Ansible job executions, failures, changes, deployments, and more within Dynatrace.  For additional monitoring of Ansible, check out the Ansible Telegraf module for Dynatrace.

Requirements
------------

Works on Linux and Windows target hosts.
Requires only the (native) uri or win_uri modules.
Dynatrace OneAgent v1.201+
OneAgent metric API enabled on target hosts.

Role Variables
--------------

### dynatrace (dt) variables
* dt_metrics_ingest_url: http://localhost:14499/metrics/ingest -> http endpoint for OneAgent metric API
* dt_metrics_group: default -> metric group (ansible.group-name.metric-name)
* dt_metrics_name: default -> metric name (ansible.group-name.metric-name)
### ansible (awx) variables
* awx_job_type: default -> the type of job (i.e. deployment, change, configuration, patching, etc) used for reporting
* awx_job_id: 0 -> the id of the job
* awx_job_template: default -> the job template
* awx_job_launch_type: default -> the method in which the job was launched

Dependencies
------------

No external role dependencies

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }


Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
