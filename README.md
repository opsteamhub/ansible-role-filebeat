#### Ansible Role: Filebeat

Installs Filebeat on RedHat/CentOS and Debian/Ubuntu

###### Example
```
Clone repository
Access repository

Change hosts on hosts file.
example:

[ec2]
"hostname" ansible_host="IP Instance" ansible_ssh_private_key_file="Keypar file"
rafael-teste ansible_host=18.231.108.60 ansible_ssh_private_key_file=~/rafael.pem

Change variables on role-filebeat/vars/main.yml

filebeat_output_elasticsearch_hosts:
  - "https://URL_ELASTICSEARCH:443"
filebeat_output_elasticsearch_username: "elasticsearch_user"
filebeat_output_elasticsearch_password: "elasticsearch_pass"

## pass paths logs
filebeat_inputs:
  - type: log
    paths:
      - "/var/log/*.log"
      - "/var/log/nginx/access.log"

execute

ansible-playbook -e vars/main.yml -b main.yml -i hosts -u ubuntu 
```
