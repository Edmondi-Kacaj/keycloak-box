# Group Vars

inside ../group_vars/all.yml file is a file that contains variables that are accessible by all roles, if you want to override them you can override same as default variables, by that you can copy and pase those variables, in you inventory_<local,test,prod>.yml

### Configuration variables

``` yml
---
# keycloak host
keycloak_host: 192.168.98.112

# keycloak base directory
keycloak_base_dir: "{{ansible_env.HOME}}"

# keycloak version (tested with 21.1.1 and above)
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