# Ansible Role NTP
[![CI](https://github.com/supertarto/ansible-role-ntp/actions/workflows/ci.yml/badge.svg)](https://github.com/supertarto/ansible-role-ntp/actions/workflows/ci.yml)

Configure a NTP client on Debian, using timesyncd, with Ansible

## Requirements
None

## Tested plateform
* Debian 12 (Bookworm)
* Debian 13 (Trixie)

## Role variables
List of NTP server to get the time from.

```yml
ntp_servers:
    - server 0.debian.pool.ntp.org
```

Your Timz Zone

```yml
ntp_time_zone: "Europe/Paris"
```

## Examples

```yml
---
- hosts: somehost
  roles:
    - supertarto.ntp
  vars:
    ntp_servers: myserver1
```

## Installation

```bash
ansible-galaxy role install supertarto.ntp
```

## License
GPL V3.0
