# updates

A role to apply software updates, via a proxy if defined.

## Requirements

Uses the following Core Ansible modules:
apt, lineinfile, wait_for

## Role Variables

| Variable | Description | Default Value |
| -------- | ----------- | ------------- |
| pfsense_proxy_host | Proxy host | 10.2.0.1 |
| pfsense_proxy_port | Proxy port | 3128 |

## Dependencies

Requires APT support.

## Example Playbook

Complete example:

    - hosts: servers
      roles:
         - { role: updates }

## License

BSD

## Author Information

> Chris Lindbergh
