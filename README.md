# ansible-role-tcp_bbr

[![Build Status](https://travis-ci.com/linuxhq/ansible-role-tcp_bbr.svg?branch=master)](https://travis-ci.com/linuxhq/ansible-role-tcp_bbr)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-tcp_bbr-blue.svg?style=flat)](https://galaxy.ansible.com/linuxhq/tcp_bbr)
[![License](https://img.shields.io/badge/license-GPLv3-brightgreen.svg?style=flat)](COPYING)

RedHat - TCP Bottleneck Bandwidth and RRT

## Requirements

 * kernel >= 4.9

## Role Variables

    tcp_bbr_modules:
      - sch_fq
      - tcp_bbr
    tcp_bbr_settings:
      - token: net.core.default_qdisc
        value: fq
      - token: net.ipv4.tcp_congestion_control
        value: bbr
    tcp_bbr_sysctl: /etc/sysctl.d/10-tcp_bbr.conf

## Dependencies

None

## Example Playbook

    - hosts: linuxhq
      roles:
        - linuxhq.tcp_bbr

## License

Copyright (C) 2021 Taylor Kimball <tkimball@linuxhq.org>

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
