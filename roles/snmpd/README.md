# [snmpd](#snmpd)

Install and configure snmpd on your system.

|GitHub|GitLab|Quality|Downloads|Version|Issues|Pull Requests|
|------|------|-------|---------|-------|------|-------------|
|[![github](https://github.com/buluma/ansible-role-snmpd/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-snmpd/actions)|[![gitlab](https://gitlab.com/buluma/ansible-role-snmpd/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-snmpd)|[![quality](https://img.shields.io/ansible/quality/58837)](https://galaxy.ansible.com/buluma/snmpd)|[![downloads](https://img.shields.io/ansible/role/d/58837)](https://galaxy.ansible.com/buluma/snmpd)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-snmpd.svg)](https://github.com/buluma/ansible-role-snmpd/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-snmpd.svg)](https://github.com/buluma/ansible-role-snmpd/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-snmpd.svg)](https://github.com/buluma/ansible-role-snmpd/pulls/)|

## [Example Playbook](#example-playbook)

This example is taken from `molecule/default/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: buluma.snmpd
```

The machine needs to be prepared. In CI this is done using `molecule/default/prepare.yml`:
```yaml
---
- name: prepare
  hosts: all
  become: yes
  gather_facts: no

  roles:
    - role: buluma.bootstrap
```


## [Role Variables](#role-variables)

The default values for the variables are set in `defaults/main.yml`:
```yaml
---
# defaults file for snmpd

snmpd_security_names:
  - name: notConfigUser
    source: default
    community: public

snmpd_groups:
  - name: notConfigGroup
    security_model: v1
    security_name: notConfigUser
  - name: NotConfigGroup
    security_model: v2c
    security_name: NotConfigUser

snmpd_views:
  - name: systemview
    type: included
    subtree: ".1.3.6.1.2.1.1"
  - name: systemview
    type: included
    subtree: ".1.3.6.1.2.1.25.1.1"

snmpd_accesses:
  - group: notConfigGroup
    context: ""
    security_model: any
    security_level: noauth
    prefix: exact
    read: systemview
    write: none
    notif: none

snmpd_syslocation: Unknown
snmpd_syscontact: Root <root@localhost>

snmpd_dontlogtcpwrappersconnects: "yes"

# snmpd_processes:
#   - name: mountd
#   - name: ntalkd
#     maximum: 4
#   - name: sendmail
#     minimum: 1
#     maximum: 10
#
# snmpd_scripts:
#   - name: shelltest
#     program: /bin/sh
#     arguments: /tmp/shtest

snmpd_disks:
  - path: /
    minimum: 10000

snmpd_load:
  one_minute_average: 12
  five_minute_average: 14
  fifteen_minute_average: 14
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-snmpd/blob/main/requirements.txt).

## [Status of used roles](#status-of-requirements)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-bootstrap)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-snmpd/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|alpine|all|
|amazon|Candidate|
|el|all|
|debian|all|
|fedora|all|
|opensuse|all|
|ubuntu|all|

The minimum version of Ansible required is 2.10, tests have been done to:

- The previous version.
- The current version.
- The development version.



If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-snmpd/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-snmpd/blob/master/CHANGELOG.md)

## [License](#license)

Apache-2.0

## [Author Information](#author-information)

[buluma](https://buluma.github.io/)
