# Ansible NTP
[![Build Status](https://travis-ci.org/supertarto/ansible-ntp.svg?branch=master)](https://travis-ci.org/supertarto/ansible-ntp)
Install and configure a NTP client with Ansible

## Requirements
None
## Tested plateform
* Debian 10 (Buster)

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
```
ansible-galaxy install supertarto.ntp
```
## License
GPL V3.0
