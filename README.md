# Ansible NTP
[![CI](https://github.com/supertarto/ansible-ntp/workflows/CI/badge.svg?event=push)](https://github.com/supertarto/ansible-ntp/actions?query=workflow%3ACI)

Install and configure a NTP client with Ansible

## Requirements
None

## Tested plateform
* Debian 10 (Buster)
* Debian 11 (Bullseye)
* Debian 12 (Bookworm)

## Role variables
List of NTP server to get the time from.

```yml
ntp-servers:
    - server 0.debian.pool.ntp.org
```

List of client restrictions. Default should be sufficient, but you can read the ntp documentation for more usage.

```yml
ntp_restricts:
  - "-4 default kod notrap nomodify nopeer noquery limited"
  - "-6 default kod notrap nomodify nopeer noquery limited"
  - "127.0.0.1"
```

## Examples

```yml
---
- hosts: somehost
  roles:
    - supertarto.ntp
  vars:
    ntp-servers:
        - myserver1
        - myserver2  
```

## Installation

```bash
ansible-galaxy role install supertarto.ntp
```

## License
GPL V3.0
