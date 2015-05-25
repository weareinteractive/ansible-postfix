# Ansible Postfix Role

[![Build Status](https://img.shields.io/travis/weareinteractive/ansible-postfix.svg)](https://travis-ci.org/weareinteractive/ansible-postfix)
[![Galaxy](http://img.shields.io/badge/galaxy-franklinkim.postfix-blue.svg)](https://galaxy.ansible.com/list#/roles/1409)
[![GitHub Tags](https://img.shields.io/github/tag/weareinteractive/ansible-postfix.svg)](https://github.com/weareinteractive/ansible-postfix)
[![GitHub Stars](https://img.shields.io/github/stars/weareinteractive/ansible-postfix.svg)](https://github.com/weareinteractive/ansible-postfix)

> `postfix` is an [ansible](http://www.ansible.com) role which:
>
> * installs postfix
> * optionally catches all mails and redirect them to a user
> * optionally listens to local interface only
> * configures service

## Installation

Using `ansible-galaxy`:

```
$ ansible-galaxy install franklinkim.postfix
```


Using `requirements.yml`:

```
- src: franklinkim.postfix
```


Using `git`:

```
$ git clone https://github.com/weareinteractive/ansible-postfix.git franklinkim.postfix
```

## Variables

Here is a list of all the default variables for this role, which are also available in `defaults/main.yml`.

```
# listen only on local interface
postfix_listen_local_only: yes

# redirect all mails
postfix_redirect_local: no
# redirect all mails user
postfix_redirect_local_user: root

# start on boot
postfix_service_enabled: yes
# current state: started, stopped
postfix_service_state: started
```

## Handlers

These are the handlers that are defined in `handlers/main.yml`.

* `restart postfix`

## Example playbook

```
- hosts: all
  sudo: yes
  roles:
    - franklinkim.postfix
  vars:
    postfix_redirect_local: yes
    postfix_listen_local_only: yes
    postfix_redirect_local_user: root
```

## Testing

```
$ git clone https://github.com/weareinteractive/ansible-postfix.git
$ cd ansible-postfix
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
