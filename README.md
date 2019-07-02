# ansible playbook GitLab Runner with supervisord

Ansible playbook for installing and configuring a [GitLab Runner](https://docs.gitlab.com/runner/).
There are other ansible playbooks for GitLab Runner, like [haroldb/ansible-gitlab-runner](https://github.com/haroldb/ansible-gitlab-runner) or [debops/ansible-gitlab_runner](https://github.com/debops/ansible-gitlab_runner), but these need root access.

This role is based on [Gitlab Runner for uberspace](https://lab.uberspace.de/guide_gitlab-runner.html):

* using [supervisord](https://manual.uberspace.de/daemons-supervisord.html)
* works in userspace (no root)
* downloads sources from amazonaws.com, does not use a package manager (apt, yum)

## Usage

Get your registration_token from https://gitlab.com/USERGROUP/PROJECT/-/settings/ci_cd#js-runners-settings or your own GitLab.


```
ansible-playbook install.yaml -i <inventory>.yaml -e "REGISTRATION_TOKEN=MyToKeNfRoMmYGitLab"
```


Optional paramter:


```
ansible-playbook install.yaml -i <inventory>.yaml -e "REGISTRATION_TOKEN=MyToKeNfRoMmYGitLab" -e "CI_SERVER_URL: https://gitlab.com" -e "TAG_LIST: master" -e "EXECUTOR: shell"

```
