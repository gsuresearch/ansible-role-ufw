# Ansible Ufw Role

[![Build Status](https://travis-ci.org/weareinteractive/ansible-ufw.png?branch=master)](https://travis-ci.org/weareinteractive/ansible-ufw)
[![Stories in Ready](https://badge.waffle.io/weareinteractive/ansible-ufw.svg?label=ready&title=Ready)](http://waffle.io/weareinteractive/ansible-ufw)

> `ufw` is an [ansible](http://www.ansible.com) role which: 
> 
> * installs ufw 
> * configures ufw rules
> * configures service

## Installation

Using `ansible-galaxy`:

```
$ ansible-galaxy install franklinkim.ufw
```

Using `arm` ([Ansible Role Manager](https://github.com/mirskytech/ansible-role-manager/)):

```
$ arm install franklinkim.ufw
```

Using `git`:

```
$ git clone https://github.com/weareinteractive/ansible-ufw.git
```

## Variables

Here is a list of all the default variables for this role, which are also available in `defaults/main.yml`.

```
# ufw_rules:
#   - { port: 22 }
#   - { port: 80, rule: allow, proto: any }
#

# list of rules
ufw_rules: []
# firewall state: enabled | disabled
ufw_state: enabled

```

## Example playbook

```
- host: all
  roles: 
    - franklinkim.ufw
  vars:
    ufw_rules:
      - { port: 22 }
      - { port: 80, rule: allow }
    ufw_state: enabled
```

## Testing

```
$ git clone https://github.com/weareinteractive/ansible-ufw.git
$ cd ansible-ufw
$ vagrant up
```

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests and examples for any new or changed functionality.

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## License
Copyright (c) We Are Interactive under the MIT license.
