# Ansible role [bareos_console](https://galaxy.ansible.com/ui/standalone/roles/buluma/bareos_console/documentation)

Install and configure [Bareos](https://www.bareos.com/) Console (bconsole) on your system.

|GitHub|Version|Issues|Pull Requests|Downloads|
|------|-------|------|-------------|---------|
|[![github](https://github.com/buluma/ansible-role-bareos_console/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bareos_console/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bareos_console.svg)](https://github.com/buluma/ansible-role-bareos_console/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-bareos_console.svg)](https://github.com/buluma/ansible-role-bareos_console/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-bareos_console.svg)](https://github.com/buluma/ansible-role-bareos_console/pulls/)|[![Ansible Role](https://img.shields.io/ansible/role/d/buluma/bareos_console)](https://galaxy.ansible.com/ui/standalone/roles/buluma/bareos_console/documentation)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-bareos_console/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true

  roles:
    - role: buluma.bareos_console
      bareos_console_directors:
        - name: bareos-dir
          address: localhost
          password: "MySuperSecretPassword"
          description: "Bareos Console credentials for local Director"
          tls_enable: true
          tls_verify_peer: false
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-bareos_console/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  become: true
  gather_facts: false

  roles:
    - role: buluma.bootstrap
    - role: buluma.bareos_repository
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-bareos_console/blob/master/defaults/main.yml):

```yaml
---
# defaults file for bareos_console

bareos_console_directors: []
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-bareos_console/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | Version |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Ansible Molecule](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bootstrap.svg)](https://github.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.bareos_repository](https://galaxy.ansible.com/buluma/bareos_repository)|[![Ansible Molecule](https://github.com/buluma/ansible-role-bareos_repository/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bareos_repository/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bareos_repository.svg)](https://github.com/shadowwalker/ansible-role-bareos_repository)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-bareos_console/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Debian](https://hub.docker.com/r/buluma/debian)|bullseye|
|[EL](https://hub.docker.com/r/buluma/enterpriselinux)|8, 9|
|[Fedora](https://hub.docker.com/r/buluma/fedora)|38, 39|
|[opensuse](https://hub.docker.com/r/buluma/opensuse)|all|
|[Ubuntu](https://hub.docker.com/r/buluma/ubuntu)|jammy|

The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-bareos_console/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-bareos_console/blob/master/CHANGELOG.md)

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-bareos_console/blob/master/LICENSE)

## [Author Information](#author-information)

[Shadow Walker](https://buluma.github.io/)
