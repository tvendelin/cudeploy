# mariadb Ansible role for Cuboid Web Application

Installs mariadb, runs a non-interactive equivalent of `mysql_secure_installation` script and
creates a database schema for Cuboid webapp.

Two additional users are created:
- `cuboid` is the username for the application 
- `admin` is a mysql superuser that can login from a non-root POSIX account from `localhost` using
  password authentication.

The following snippet from Ansible's `hosts` covers the variables that must be defined for all hosts
that either run the database instance or connect to it.

```
all:
  vars:
    mariadb:
      admin_user: admin
      admin_password: '1234'
      app_user: cuboid
      app_password: 'change_it'
      app_db: cuboid
```

The role is intended for a standalone DB host and does not cater for any database clustering.

