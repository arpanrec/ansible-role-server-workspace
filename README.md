Development apps
=========

Install server workspace apps (with tags)

* Java (java)

Role Variables
--------------

`rv_server_ws_apps_def_packages`

* Type: `List<String>`
* Required: `false`
* Default: ['rclone','openjdk-11-jdk','maven','groovy','gradle']
* Description: Install packages for workspace applications

Example Playbook
----------------

```
- name: Install dev workspace apps
  include_role:
    name: server_workspace
```

License
-------

`Apache License 2.0`
