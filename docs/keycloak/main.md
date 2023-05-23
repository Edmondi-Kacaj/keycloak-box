# Keycloak Information

[__Keycloak__](https://www.keycloak.org/) is a tool for “Identity and Access Management”, as written on their project page on GitHub. Additionally, Keycloak is an open-source tool currently licensed with Apache License 2.0. It is also an upstream project for Red Hat SSO, so if you are looking for something more enterprise-centered, you can check it.

### Configuration variables

They are multiple configuration variables, that you can override based on your needs, and if you need to change or override base in you requirement, that you can copy and pase those variables, in you inventory_<local,test,prod>.yml 


```yml
# System Group name, is used to create a group for keycloak in the server
keycloak_group_name: keycloak

# folder name,
keycloak_folder_name: "keycloak-{{keycloak_version}}"
# location in server
keycloak_location: "/opt"
# URL of of keycloak installation
keycloak_url: "https://github.com/keycloak/keycloak/releases/download/{{keycloak_version | default('21.1.1',true)}}/keycloak-{{keycloak_version | default('21.1.1',true)}}.zip"
# Keycloak config file
keycloak_conf_file: keycloak.conf.j2

# Default postgres root password
keycloak_postgres_tmp_root_password: xxx
# List of all configuration check the link https://www.keycloak.org/server/all-config
# LOGS CONFIGURATION see https://www.keycloak.org/server/all-config#category-logging
# Enable keycloak logs
keycloak_log_enable: true
# Log handlers, you can use more than one, example: console,file
keycloak_log_handlers: "file"
# Log format
keycloak_log_format: '%d{yyyy-MM-dd HH:mm:ss,SSS} %-5p [%c] (%t) %s%e%n'

# Postgres database 
keycloak_db_type: postgres
# Postgres database port
keycloak_postgresql_port: 5432
# Postgres database backup, absent=deactivate / present=activate
keycloak_backup_process_state: absent
# Postgres database backup user
keycloak_backup_db_user: keycloakbackup
# Postgres database backup password
keycloak_backup_db_password: changeme
# Postgres database backup schedule hours
keycloak_backup_schedule_hour: 2
# Postgres database backup path
keycloak_backup_path: '{{ base_dir }}/backup'


# enable/disable keycloak heath
keycloak_health_enabled: true
# enable/disable keycloak metric
keycloak_metrics_enabled: true
# keycloak enable features, can have multiple separated by comma, 
#  example: "token-exchange, update-email, web-authn"
keycloak_feature_enabled: "token-exchange"
# keycloak disable features, can have multiple separated by comma, 
#  example: "token-exchange, update-email, web-authn"
keycloak_feature_disabled: 

```

## Templates folder

inside the templates folder they are 2 configuration files

1) __keycloak.conf.j2__ ==> which includes all the configuration we need for keycloak in order to work, if you want to adjust it then you can modify it, or if you are using the __keycloak-box__ as a submodule, then create another file and then update the configuration variable in that you can copy and pase those variables, in you inventory_<local,test,prod>.yml, to call your custom file

```yml
# Keycloak config file
keycloak_conf_file: <path>/you-custom-keycloak.conf.j2
```

2) __keycloak.service.j2__ is a service file that is used to run the keycloak as a systemd service.