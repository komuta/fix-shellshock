Ansible playbook aiming at fixing [ShellShock](http://www.troyhunt.com/2014/09/everything-you-need-to-know-about.html) vulnerability.

## Compatibility

* Debian 6 and after
* Ubuntu 12.04 & 14.04
* CentOS 6

## Usage

Dry-run mode:
```
$ ansible-playbook -i inventory fix_shellshock.yml -vC
```

Fixing servers:
```
$ ansible-playbook -i inventory fix_shellshock.yml -v
```

## Description

This playbook is actually pretty simple: it checks targets servers for the vulnerability, fails if the machine is not vulnerable, and upgrade bash package to the latest version. To ensure the fix has succeed, re-run the playbook in dry-run mode.

### Special note regarding Debian Squeeze

Has Debian Squeeze has been superseeded by Wheezy and entered LTS since 2014, June 1st, the playbook ensures squeeze-lts repository is configured.
