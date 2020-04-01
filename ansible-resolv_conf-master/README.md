
resolv_conf
===========

[![Build Status](https://github.com/horrada/ansible-resolv.conf)

Configures /etc/resolv.conf file

Requirements
------------

This role requires Ansible 2.93 or higher.

Role Variables
--------------

| Name                       | Default                  | Description                     |
|:---------------------------|:-------------------------|:--------------------------------|
| resolv_conf_nameservers    | ['8.8.8.8', '8.8.4.4']   | List of nameserver IP addresses |
| resolv_conf_search_domains | ["{{ ansibledomain }}"]  | List of search domains          |

Dependencies
------------

None

Example Playbook
----------------

Configure /etc/resolv.conf file specifying nameservers and a search domain
```yaml
- hosts: all
  vars:
    resolv_conf_nameservers:
      - 8.8.4.4
      - 8.8.8.8
    resolv_conf_search_domains:
      - example.com
  roles:
    - resolv_conf
```

Configure /etc/resolv.conf file with group_vars values allows separate environments
```yaml
- hosts: all
  roles:
    - resolv_conf
```

Configure /etc/resolv_conf with no values will fail and this is deliberate, but can be configured with default values.


License
-------

Author Information
------------------

Adam Horrell
