# Ansible Role for deploying a Nextcloud container
This role deploys de latest version of the nextcloud container and optionally sets up a database container with MariaDB or MySQL. Currently de only options.
## Requirements
This role requires that docker-compose it's already installed on the target machine. For that you can use @geerlingguy rol for [docker](https://github.com/geerlingguy/ansible-role-docker).
## Role Variables
The current variables are as follow:
```yml
# Path for saving config of docker
nextcloud_docker_volume_base_path: "/opt/app/nextcloud"
# Username and password for admin
nextcloud_docker_admin_username: user
nextcloud_docker_admin_password: changeme
# Http port, https not currently enabled
nextcloud_docker_http_port: 8080
# More types will be supported on the future
nextcloud_database_type: sqlite 
# User and password for database
nextcloud_database_password: changeme
nextcloud_database_path: "/opt/app/database"
# Trusted domains
nextcloud_docker_trusted_domains:
  - "{{ ansible_default_ipv4.address }}"
  - 127.0.0.1
# PHP limits
nextcloud_docker_php_memory_limit: 512M
nextcloud_docker_php_upload_limit: 512M
# Debug option for clearing containers and volumes
nextcloud_docker_clear: false
```