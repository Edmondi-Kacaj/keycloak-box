# Inventory Local

__inventory_local.yml__ is an example (This file with run in same machine as vagrant use) how you are gonna run the __keycloak-box__ in a server.
They are multiple  default configuration variables (see in each role), that you can override based on your needs, that you can copy and pase those variables, in you __inventory_local.yml__.


## Structure 

```yml
keycloak:
  hosts:
    192.168.98.112:
      ansible_ssh_user: vagrant
      ansible_ssh_private_key_file: ~/.vagrant.d/insecure_private_key

      # keycloak base directory
      keycloak_base_dir: "{{ansible_env.HOME}}"

      # keycloak version 
      keycloak_version: 21.1.1
  
      # initial user administration
      keycloak_initial_admin:
        username: admin
        password: ch@ngEme
  
      # keycloak database configuration
      keycloak_db:
        name: keycloak
        user: keycloak
        password: keycloak
  
      # keycloak port
      keycloak_http_port: 8008
      #  keycloak relative path, this will be used also in reverse proxy nginx
      keycloak_http_relative_path: keycloak

```

As I mention above here you can use the default variable from each roles if you want to override them.


## Example of running

you need to have ansible installed in you computer. (maybe ansible in Windows will not work)
then you can: 
```sh
    # First install requirement
     ansible-galaxy install -r requirements.yml
    #  then you just run the ansible-playbook
     ansible-playbook -v -i inventory_local.yml ansible/playbook.yml 
```