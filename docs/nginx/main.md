# NGINX

Nginx is a web server that can also be used as a reverse proxy, load balancer, mail proxy and HTTP cache.we use nginx as a reverso proxy for keycloak.



### Configuration variables

Nginx role use some default variables, and if you need to change or override base in you requirement, that you can copy and pase those variables, in you inventory_<local,test,prod>.yml

```yml
---
# Nginx v-host files
# By default we already created and configured the the basic configuration for nginx in order to make it work
nginx_configuration_files:
  - ["keycloak-vhost.conf.j2", "keycloak-vhost.conf"]


# If you want to override it, then copy this variable, into inventory_<local,test,prod>.yml, and give you own configuration file

#example: 
nginx_configuration_files:
  - ["<path>/keycloak-example.conf.j2", "keycloak-example.conf"]


# Since we are using variable, inside the file, we are using .j2 template so ansible will replace those variables 
```