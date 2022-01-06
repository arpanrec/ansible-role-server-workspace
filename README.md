Development apps
=========

Install server workspace apps (with tags)

* Java (java)

Role Variables
--------------
`rv_server_ws_apps_def_packages_{{  ansible_distribution  }}`
  * Type: `List<String>`
  * Required: `false`
  * Default (rv_server_ws_apps_def_packages_Debian): ['rclone','openjdk-11-jdk','maven','groovy','gradle']
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
