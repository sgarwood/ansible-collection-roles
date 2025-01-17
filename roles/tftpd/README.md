# [tftpd](#tftpd)

Install and configure tftpd on your system.

|GitHub|GitLab|Quality|Downloads|Version|Issues|Pull Requests|
|------|------|-------|---------|-------|------|-------------|
|[![github](https://github.com/buluma/ansible-role-tftpd/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-tftpd/actions)|[![gitlab](https://gitlab.com/buluma/ansible-role-tftpd/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-tftpd)|[![quality](https://img.shields.io/ansible/quality/58378)](https://galaxy.ansible.com/buluma/tftpd)|[![downloads](https://img.shields.io/ansible/role/d/58378)](https://galaxy.ansible.com/buluma/tftpd)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-tftpd.svg)](https://github.com/buluma/ansible-role-tftpd/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-tftpd.svg)](https://github.com/buluma/ansible-role-tftpd/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-tftpd.svg)](https://github.com/buluma/ansible-role-tftpd/pulls/)|

## [Example Playbook](#example-playbook)

This example is taken from `molecule/default/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: Converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: buluma.tftpd
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
    # - role: buluma.xinetd
```



## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-tftpd/blob/main/requirements.txt).

## [Status of used roles](#status-of-requirements)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-bootstrap)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-tftpd/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|amazon|Candidate|
|el|8|
|debian|all|
|fedora|all|
|opensuse|all|
|ubuntu|all|

The minimum version of Ansible required is 2.10, tests have been done to:

- The previous version.
- The current version.
- The development version.

## [Exceptions](#exceptions)

Some roles can't run on a specific distribution or version. Here are some exceptions.

| variation                 | reason                 |
|---------------------------|------------------------|
| Alpine | xinetd (missing) |
| Archlinux | target not found: tftpd |


If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-tftpd/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-tftpd/blob/master/CHANGELOG.md)

## [License](#license)

Apache-2.0

## [Author Information](#author-information)

[buluma](https://buluma.github.io/)
