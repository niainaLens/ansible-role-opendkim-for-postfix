# Ansible Role: Opendkim for postfix

Install opendkim & set configs on Debian/Ubuntu.\
Ansible role created from steps on this [tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-dkim-with-postfix-on-debian-wheezy).

## Requirements

**OS**: debian/ubuntu based distro
**Package**: 	postfix installed & operational

## Role Variables

Needed variables are listed below, along with default values (see `defaults/main.yml`):

to edit:

- vars into file: /etc/opendkim/TrustedHosts 

```
ip_trusted: '1.2.3.4/24'
domain_trusted: '*.mysite.com'
```

- var into file: /etc/opendkim/KeyTable, /etc/opendkim/SigningTable\
  &\
  directory name: /etc/opendkim/keys/{{ domain_com }}

```
domain_com: mysite.com
```


## Dependencies

None.

## Example Playbook

    - hosts: mail_server
      become: yes
      roles:
        - postfix
        - opendkim_for_postfix

## License

MIT / BSD

## Author Information

by Niaina Lens.
