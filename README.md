# ansible-role-dome9agent

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-dome9agent.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-dome9agent)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-dome9agent-blue.svg?style=flat)](https://galaxy.ansible.com/linuxhq/dome9agent)
[![License](https://img.shields.io/badge/license-GPLv3-brightgreen.svg?style=flat)](COPYING)

RHEL/CentOS - Dome9 Cloud Infrastructure Security

## Requirements

This role requires that you have the dome9 repository installed.

 * https://galaxy.ansible.com/linuxhq/dome9/

## Role Variables

Available variables are listed below, along with default values:

    dome9_agent_debug: false
    dome9_agent_pair_key: generic_prod.pem
    dome9_agent_pair_cert: generic_prod.pem
    dome9_agent_run_dir: /var/lib/dome9
    dome9_connection_ca_certs: ca-certs.pem
    dome9_connection_cert_enforce: true
    dome9_connection_host: agents.dome9.com
    dome9_connection_port: 443
    dome9_firewall_allow_icmp: false
    dome9_firewall_allow_ipsec: false
    dome9_firewall_enable_ftp: true
    dome9_firewall_enforce_outbound: true
    dome9_firewall_synflood_protect: false
    dome9_install_pairkey: ''
    dome9_install_secgroups: []
    dome9_poller_ca_certs: ca-certs.pem
    dome9_poller_enabled: true
    dome9_poller_host: notifications.dome9.com
    dome9_poller_nossl: false
    dome9_poller_port: 443

The following variables are __**required**__:

    dome9_install_pairkey: ''
    dome9_install_secgroups: []

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.dome9agent
          dome9_firewall_enable_ftp: false
          dome9_firewall_synflood_protect: true
          dome9_install_pairkey: hq92aalptp2c6es2me
          dome9_install_secgroups:
            - whitelist-dns
            - whitelist-external
            - whitelist-internal

## License

Copyright (C) 2018 Taylor Kimball <tkimball@linuxhq.org>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <http://www.gnu.org/licenses/>.
