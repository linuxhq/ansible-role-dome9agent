# ansible-role-dome9agent

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-dome9agent.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-dome9agent)

RHEL/CentOS - Dome9 Cloud Infrastructure Security

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    dome9_agent_debug: False
    dome9_agent_pair_key: generic_prod.pem
    dome9_agent_pair_cert: generic_prod.pem
    dome9_agent_run_dir: /var/lib/dome9
    dome9_connection_ca_certs: ca-certs.pem
    dome9_connection_cert_enforce: True
    dome9_connection_host: agents.dome9.com
    dome9_connection_port: 443
    dome9_firewall_enable_ftp: True
    dome9_firewall_synflood_protect: False
    dome9_poller_ca_certs: ca-certs.pem
    dome9_poller_enabled: True
    dome9_poller_host: notifications.dome9.com
    dome9_poller_port: 443

You must modify these varibles.  The pairkey is used to register your node, and the secgroups
must be defined so you can access your node.

    dome9_install_pairkey: xxxxxxxxxxxxxxxxxx
    dome9_install_secgroups:
      - secgroup1
      - secgroup2

## Dependencies

 * https://galaxy.ansible.com/linuxhq/dome9/

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.dome9agent
          dome9_firewall_enable_ftp: False
          dome9_firewall_synflood_protect: True
          dome9_install_pairkey: xxxxxxxxxxxxxxxxxx
          dome9_install_secgroups:
            - secgroup1
            - secgroup2
            - secgroup3

## License

BSD

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
