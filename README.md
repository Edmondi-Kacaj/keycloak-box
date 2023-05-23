# Keycloak Box



Installation of Keycloak via ansible.
## Installation on local system for testing

Prerequisites
* [Git](https://git-scm.com/downloads)
* [Vagrant](https://www.vagrantup.com/downloads.html)
* [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

Perform the following steps in the terminal (Linux / macOS) or in the GitBash (Windows).
```
git clone https://gitlab.com/e.kacaj/keycloak-box.git
cd keycloak-box
vagrant up
```

When the installation is complete (a few minutes, depending on the download speed), keycloak can be opened in the browser

<http://192.168.98.117/keycloak> 
```sh
    #Administration Console  
    username/email:  admin
    password:        ch@ngEme
```



