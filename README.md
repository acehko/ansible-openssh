# Ansible Role: OpenSSH
[![Build Status](https://travis-ci.com/acehko/ansible-openssh.svg?branch=master)](https://travis-ci.com/acehko/ansible-openssh)

Ansible role used to install and configure OpenSSH.

## Supported Platforms
- Arch Linux
- Debian Buster

## Requirements
- **gather_facts** is required for OS detection.

## Role Variables
| Variable                    | Default | Description                                                                         |
|:----------------------------|:--------|:------------------------------------------------------------------------------------|
| **openssh_mosh**            | `false` | Whether to install `mosh`.                                                          |
| **openssh_config**          |         | Any configuration defined here will be applied to the OpenSSH Server configuration. |
| **openssh_authorized_keys** | `[]`    | A list of authorized keys for users.                                                |

## Dependencies
None.

## Example Playbook
```yaml
- hosts: all
  gather_facts: yes
  roles:
    - role: acehko.openssh
      openssh_mosh: true
      openssh_config:
        Port: 1213
        PasswordAuthentication: "no"
      openssh_authorized_keys:
        - user: user
          keys:
            - "ssh-ed25519 XXXXXXXXXXXXXXXXXXXX user@host"
```

## License
[MIT](LICENSE)

## Author Information
[Andrija Čehko](https://github.com/acehko)
