# [molecule](#molecule)

Install Molecule on your system.

|GitHub|GitLab|Quality|Downloads|Version|Issues|Pull Requests|
|------|------|-------|---------|-------|------|-------------|
|[![github](https://github.com/buluma/ansible-role-molecule/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-molecule/actions)|[![gitlab](https://gitlab.com/buluma/ansible-role-molecule/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-molecule)|[![quality](https://img.shields.io/ansible/quality/57954)](https://galaxy.ansible.com/buluma/molecule)|[![downloads](https://img.shields.io/ansible/role/d/57954)](https://galaxy.ansible.com/buluma/molecule)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-molecule.svg)](https://github.com/buluma/ansible-role-molecule/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-molecule.svg)](https://github.com/buluma/ansible-role-molecule/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-molecule.svg)](https://github.com/buluma/ansible-role-molecule/pulls/)|

## [Example Playbook](#example-playbook)

This example is taken from `molecule/default/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: Converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: buluma.molecule
```

The machine needs to be prepared. In CI this is done using `molecule/default/prepare.yml`:
```yaml
---
- name: Prepare
  hosts: all
  gather_facts: no
  become: yes

  roles:
    - role: buluma.bootstrap
    - role: buluma.buildtools
    - role: buluma.epel
    - role: buluma.python_pip
```


## [Role Variables](#role-variables)

The default values for the variables are set in `defaults/main.yml`:
```yaml
---
# defaults file for molecule

# If you need to give extra options to pip, use `molecule_extra_args`. For
# example:
# molecule_extra_args: "--user"
molecule_extra_args: ""
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-molecule/blob/main/requirements.txt).

## [Status of used roles](#status-of-requirements)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-bootstrap)|
|[buluma.buildtools](https://galaxy.ansible.com/buluma/buildtools)|[![Build Status GitHub](https://github.com/buluma/ansible-role-buildtools/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-buildtools/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/ansible-role-buildtools/badges/main/pipeline.svg)](https://gitlab.com/buluma/ansible-role-buildtools)|
|[buluma.epel](https://galaxy.ansible.com/buluma/epel)|[![Build Status GitHub](https://github.com/buluma/ansible-role-epel/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-epel/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/ansible-role-epel/badges/main/pipeline.svg)](https://gitlab.com/buluma/ansible-role-epel)|
|[buluma.python_pip](https://galaxy.ansible.com/buluma/python_pip)|[![Build Status GitHub](https://github.com/buluma/ansible-role-python_pip/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-python_pip/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/ansible-role-python_pip/badges/main/pipeline.svg)](https://gitlab.com/buluma/ansible-role-python_pip)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-molecule/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|el|8|
|debian|all|
|fedora|all|
|ubuntu|focal|

The minimum version of Ansible required is 2.10, tests have been done to:

- The previous version.
- The current version.
- The development version.

## [Exceptions](#exceptions)

Some roles can't run on a specific distribution or version. Here are some exceptions.

| variation                 | reason                 |
|---------------------------|------------------------|
| centos:7 | install_requires' must be a string or list of strings containing valid project/version requirement specifiers |
| amazonlinux | Dependency (python_pip) not available |
| opensuse | UnicodeDecodeError: 'ascii' codec can't decode byte 0xc3 in position 13: ordinal not in range(128) |
| alpine | error: [Errno 2] No such file or directory: 'cargo' |


If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-molecule/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-molecule/blob/master/CHANGELOG.md)

## [License](#license)

Apache-2.0

## [Author Information](#author-information)

[buluma](https://buluma.github.io/)
