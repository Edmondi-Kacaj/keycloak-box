# Playbook

__playbook.yml__ is a file that contains a  lists of roles that are automatically execute against hosts. Groups of hosts form your Ansible inventory, in our case in __playbook.yml__ as you see below we have all the roles that need to be executed in order to install __keycloak__.

Mostly we don't change this, but if we don't want to add/delete a roles then we can adjust here


## Structure

```yml

- hosts: all
  roles:
  - role: geerlingguy.java
    become: yes
    tags:
      - java
  - role: postgres
    when: keycloak_db_type is defined and keycloak_db_type == "postgres"
    tags:
      - postgres
  - role: nginx
    tags:
      - nginx
  - role: keycloak
    become: yes
    tags:
      - keycloak
    
```