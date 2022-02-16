# cuboid Ansible role for cuboid web application

Deploys a Cuboid web app as a Python/uWSGI application, proxied by `nginx` web server over a UNIX
socket. 

The shippet from Ansible's hosts file below shows the variables that must be defined. `project.stage_dir` is
the directory on the Ansible host, where the package is built. It is assumed that the application is
deployed to the members of `cuboid` inventory group.

```
all:
  vars:
    project:
      repo: '/root/cuboid.git/.git'
      stage_dir: '/root/stage'
    mariadb:
      admin_user: admin
      admin_password: '1234'
      app_user: cuboid
      app_password: 'change_it'
      app_db: cuboid

  children:
    cuboid:
      hosts:
        85.215.239.34:
          dbhost: 85.215.233.125
      vars:
        cuboid_dir: '/opt/cuboid'
```


