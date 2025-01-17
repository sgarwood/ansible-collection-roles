# [systemd](#systemd)

Systemd, a system and service manager for Linux operating systems

|GitHub|GitLab|Quality|Downloads|Version|Issues|Pull Requests|
|------|------|-------|---------|-------|------|-------------|
|[![github](https://github.com/buluma/ansible-role-systemd/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-systemd/actions)|[![gitlab](https://gitlab.com/buluma/ansible-role-systemd/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-systemd)|[![quality](https://img.shields.io/ansible/quality/58859)](https://galaxy.ansible.com/buluma/systemd)|[![downloads](https://img.shields.io/ansible/role/d/58859)](https://galaxy.ansible.com/buluma/systemd)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-systemd.svg)](https://github.com/buluma/ansible-role-systemd/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-systemd.svg)](https://github.com/buluma/ansible-role-systemd/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-systemd.svg)](https://github.com/buluma/ansible-role-systemd/pulls/)|

## [Example Playbook](#example-playbook)

This example is taken from `molecule/default/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: Converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: buluma.systemd
```

The machine needs to be prepared. In CI this is done using `molecule/default/prepare.yml`:
```yaml
---
- name: Prepare
  hosts: all
  become: yes
  gather_facts: no

  roles:
    - role: buluma.bootstrap
    - role: buluma.systemd
```


## [Role Variables](#role-variables)

The default values for the variables are set in `defaults/main.yml`:
```yaml
---
_default_unit_path: "/etc/systemd/system"
_default_unit_type: "service"
_default_unit_enabled: "no"
_default_systemd_backup_files: true
_default_unit_state: "stopped"

unit_config: []

perform_uninstall: false
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-systemd/blob/main/requirements.txt).

## [Status of used roles](#status-of-requirements)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-bootstrap)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-systemd/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|el|all|
|debian|all|
|fedora|all|
|ubuntu|all|
|amazon|all|

The minimum version of Ansible required is 2.10, tests have been done to:

- The previous version.
- The current version.
- The development version.

## [Exceptions](#exceptions)

Some roles can't run on a specific distribution or version. Here are some exceptions.

| variation                 | reason                 |
|---------------------------|------------------------|
| Archlinux | GLIBC_2.34 not found |


If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-systemd/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-systemd/blob/master/CHANGELOG.md)

## [License](#license)

Apache-2.0

## [Author Information](#author-information)

[buluma](https://buluma.github.io/)
