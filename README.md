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

### Variables

- `pv_ua_dotfiles_git_remote`
  - Description: Git remote
  - Default: [arpanrec/dotfiles](https://github.com/arpanrec/dotfiles)
- `pv_ua_dotfiles_bare_relative_dir`
  - Description: Git bare directory in `{{ pv_ua_user_home_dir }}`
  - Default: `.dotfiles`

### Example Playbook

```yaml
- name: "Include Dotfiles"
  include_role:
    name: "arpanrec.server_workspace"
    tasks_from: dotfiles
```

### Testing

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

## License

-------

`MIT`
