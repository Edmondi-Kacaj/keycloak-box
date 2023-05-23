## Keycloak Information

[__Keycloak__](https://www.keycloak.org/) is a tool for “Identity and Access Management”, as written on their project page on GitHub. Additionally, Keycloak is an open-source tool currently licensed with Apache License 2.0. It is also an upstream project for Red Hat SSO, so if you are looking for something more enterprise-centered, you can check it.

## Keycloak Box

[Keycloak Box](https://gitlab.com/e.kacaj/keycloak-box), is an software tools that automate install/deploy the [__Keycloak__](https://www.keycloak.org/), in you server

## Documentation
[Keycloak Box](https://gitlab.com/e.kacaj/keycloak-box), contains multiple roles, that are necessary to have, in order to install the __Keycloak__ in you server

## Folder structure

    Keycloak Box
    ├── group_vars             # Contain the necessary variables to install all the roles 
    ├── roles                  # include all the roles, necessary to install keycloak 
        └── keycloak           # the keycloak role that contains all the task needed to install the keycloak in your server
        └── nginx              # nginx role, we use nginx as a reverso proxy for keycloak
        └── postgres           # postgres role is used to install postgres database, a database used by keycloak
        └── playbook.yml       # The main point, where ansible will run all the roles needed to install keycloak
    ├── docs                   # Documentation folder
    ├── inventory_local.yml    # a example of inventory used by ansible to install the keycloak locally in Virtual machine (Works only in Linux/Mac)
    └── README.md              # a readme me file

## Documentation

For each role you can find the documentation, and variables that you can use in order to adjust base in your needs

* [GROUP_VARS](/docs/group_vars/main.md)
* [NGINX](/docs/nginx/main.md)
* [POSTGRES](/docs/postgres/main.md)
* [KEYCLOAK](/docs/keycloak/main.md)
* [PLAYBOOK](/docs/playbook.md)
* [INVENTORY_LOCAL](/docs/inventory_local.md)