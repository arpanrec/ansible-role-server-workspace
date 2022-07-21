# Development apps

<details>
<summary>Track Dotfiles With GIT</summary>

## Track Dotfiles With GIT

Track your dotfiles from [GitHub](https://github.com/arpanrec/dotfiles). You can track these files with below command. (Follow the git commands for reference)

```shell
config pull # To pull the changes
config add <filepath> # Track new files/Changes
config commit -m"New Config added/Changed" # Track new files
config push # Push to remote
```

### Variables dotfiles

- `pv_ua_dotfiles_git_remote`
  - Description: Git remote
  - Default: [arpanrec/dotfiles](https://github.com/arpanrec/dotfiles)
- `pv_ua_dotfiles_bare_relative_dir`
  - Description: Git bare directory in `{{ pv_ua_user_home_dir }}`
  - Default: `.dotfiles`

### Example Playbook dotfiles

```yaml
- name: "Include Dotfiles"
  include_role:
    name: "arpanrec.server_workspace"
    tasks_from: dotfiles
```

### Testing dotfiles

Prerequisite: `docker`, `python3-pip`

```bash
git clone git@github.com:arpanrec/ansible-role-server-workspace.git arpanrec.server_workspace
cd arpanrec.server_workspace
python3 -m pip install --user --upgrade virtualenv
virtualenv --python $(readlink -f $(which python3)) venv
source venv/bin/activate
venv/bin/python3 -m pip install -r requirements.txt --upgrade
molecule test -s dotfiles
```

</details>

<details>
<summary>Utility Scripts</summary>

## Utility Scripts

---

Tag: `scripts`

Install [Utility Scripts](https://github.com/arpanrec/util-scripts/tree/main/bin) to `{{ pv_ua_user_bin_dir }}`

Variables:

- Not Applicable
  
### Example Playbook util-scripts

```yaml
- name: "Include Utility Scripts"
  include_role:
    name: "arpanrec.server_workspace"
    tasks_from: util-scripts
```

### Testing util-scripts

Prerequisite: `docker`, `python3-pip`

```bash
git clone git@github.com:arpanrec/ansible-role-server-workspace.git arpanrec.server_workspace
cd arpanrec.server_workspace
python3 -m pip install --user --upgrade virtualenv
virtualenv --python $(readlink -f $(which python3)) venv
source venv/bin/activate
venv/bin/python3 -m pip install -r requirements.txt --upgrade
molecule test -s util-scripts
```

</details>

<details>
<summary>Oracle Java</summary>

## Oracle Java

Install oracle jdk in user space

### Variables Oracle Java

- `pv_ua_jdk_install_path`
  - Description: Install path for java
  - Default: "{{  pv_ua_user_share_dir  }}/java"
- `pv_ua_jdk_version`
  - Description: Major Java Release version
  - Default: 17

### Example Playbook Oracle Java

```yaml
- name: "Include Oracle Java"
  include_role:
    name: "arpanrec.server_workspace"
    tasks_from: java
```

### Testing Oracle Java

Prerequisite: `docker`, `python3-pip`

```bash
git clone git@github.com:arpanrec/ansible-role-server-workspace.git arpanrec.server_workspace
cd arpanrec.server_workspace
python3 -m pip install --user --upgrade virtualenv
virtualenv --python $(readlink -f $(which python3)) venv
source venv/bin/activate
venv/bin/python3 -m pip install -r requirements.txt --upgrade
molecule test -s java
```

</details>

## License

---

`MIT`
