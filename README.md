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

Testing
-------

Prerequisite: `docker`, `python3-pip`

```bash
git clone git@github.com:arpanrec/ansible-role-server-workspace.git arpanrec.server_workspace
cd arpanrec.server_workspace
pip install --user --upgrade virtualenv
virtualenv venv
source venv/bin/activate
pip install -r requirements.txt
molecule test
```

License
-------

`MIT`
