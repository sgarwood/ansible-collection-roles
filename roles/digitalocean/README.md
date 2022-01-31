# [digitalocean-agent](#digitalocean-agent)

Install digitalocean agent on your system.

|GitHub|GitLab|Quality|Downloads|Version|
|------|------|-------|---------|-------|
|[![github](https://github.com/buluma/ansible-role-digitalocean-agent/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-digitalocean-agent/actions)|[![gitlab](https://gitlab.com/buluma/ansible-role-digitalocean-agent/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-digitalocean-agent)|[![quality](https://img.shields.io/ansible/quality/)](https://galaxy.ansible.com/buluma/digitalocean-agent)|[![downloads](https://img.shields.io/ansible/role/d/)](https://galaxy.ansible.com/buluma/digitalocean-agent)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-digitalocean-agent.svg)](https://github.com/buluma/ansible-role-digitalocean-agent/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from `molecule/default/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: Converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: buluma.digitalocean-agent
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
    - role: buluma.ca_certificates
    - role: buluma.apt_autostart
```

Also see a [full explanation and example](https://buluma.nl/how-to-use-these-roles.html) on how to use these roles.


## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-digitalocean-agent/blob/master/requirements.txt).

## [Status of used roles](#status-of-requirements)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.apt_autostart](https://galaxy.ansible.com/buluma/apt_autostart)|[![Build Status GitHub](https://github.com/buluma/ansible-role-apt_autostart/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-apt_autostart/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/ansible-role-apt_autostart/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-apt_autostart)|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-bootstrap)|
|[buluma.ca_certificates](https://galaxy.ansible.com/buluma/ca_certificates)|[![Build Status GitHub](https://github.com/buluma/ansible-role-ca_certificates/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-ca_certificates/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/ansible-role-ca_certificates/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-ca_certificates)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-digitalocean-agent/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|amazon|Candidate|
|el|8|
|debian|all|
|fedora|all|
|ubuntu|all|

The minimum version of Ansible required is 2.10, tests have been done to:

- The previous version.
- The current version.
- The development version.

## [Exceptions](#exceptions)

Some roles can't run on a specific distribution or version. Here are some exceptions.

| variation                 | reason                 |
|---------------------------|------------------------|
| alpine | do-agent (missing) |
| suse | No provider of '+do-agent |
| centos:latest | rpm_key is not idempotent... |


If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-digitalocean-agent/issues)

## [License](#license)

Apache-2.0

## [Author Information](#author-information)

[Michael Buluma](https://buluma.nl/)

Please consider [sponsoring me](https://github.com/sponsors/buluma).