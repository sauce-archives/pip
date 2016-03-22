# pip

[![License](https://img.shields.io/badge/license-New%20BSD-blue.svg?style=flat)](https://raw.githubusercontent.com/saucelabs-ansible/pip/master/LICENSE)
[![Build Status](https://travis-ci.org/saucelabs-ansible/pip.svg?branch=master)](https://travis-ci.org/saucelabs-ansible/pip)

[![Platform](http://img.shields.io/badge/platform-ubuntu-dd4814.svg?style=flat)](#)

[![Project Stats](https://www.openhub.net/p/saucelabs-ansible-pip/widgets/project_thin_badge.gif)](https://www.openhub.net/p/saucelabs-ansible-pip/)

Ansible role to install [pip](https://pip.pypa.io/en/stable/).


## Tests

| Family | Distribution | Version | Test Status |
|:-:|:-:|:-:|:-:|
| Debian | Debian  | Jessie  | [![x86_64](http://img.shields.io/badge/x86_64-unknown-cccccc.svg?style=flat)](#) |
| Debian | Debian  | Wheezy  | [![x86_64](http://img.shields.io/badge/x86_64-unknown-cccccc.svg?style=flat)](#) |
| Debian | Ubuntu  | Precise | [![x86](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#)  |
| Debian | Ubuntu  | Trusty  | [![x86](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu  | Vivid   | [![x86](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| RedHat | CentOS  | 6.6     | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| RedHat | Centos  | 7       | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |


## Requirements

- ansible >= 1.9.4


## Role Variables

- **debug**: flag to run debug tasks.
- **pip_dir_source**: the directory where the installer should be downloaded.
- **pip_version**: the version to be installed.

Unless stated otherwise
a default value is provided for each of the variables mentioned above
in `defaults/main.yml`.


## Dependencies

None.


## Playbooks

Example:

    - hosts: servers
      vars:
        debug: yes

      roles:
         - role: pip
           tags: [ pip ]


## Tags

- **configuration**: configuration tasks.
- **debug**: task to debug role variables.
- **installation**: installation tasks.
- **validation**: task to validate role variables.


## Test

To run the tests you will need to install:

- [tox](https://tox.readthedocs.org/)
- [vagrant](https://www.vagrantup.com/)

To run all tests against all pre-defined OS/distributions * ansible versions:

```
$ tox
```

To run tests for `trusty64`:

```
$ cd tests
$ bash test_idempotence.sh --box trusty64.vagrant.dev
# log file will be stores under tests/log
```

To perform debugging on a specific environment:

```
$ cd tests
$ vagrant up trusty64.vagrant.dev

# to provision using the test.yml playbook (as many time as you need)
$ vagrant provision trusty64.vagrant.dev

# to access the Vagrant box
$ vagrant ssh trusty64.vagrant.dev
```


## Links

- [pip](https://pip.pypa.io/en/stable/)
- [pip installation](https://pip.pypa.io/en/stable/installing/)


## Author Information

- [steenzout](https://github.com/steenzout/)
