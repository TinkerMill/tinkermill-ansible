# shell-master

A role to configure a system so it acts as a great shell system.  For example, running scripts, interacting with git & ansible, etc.

## Requirements

Uses the following Core Ansible modules:
apt, template

## Role Variables

None.

## Dependencies

None.

## Example Playbook

    - hosts: servers
      roles:
         - { role: shell-master }

## License

BSD

## Author Information

> Chris Lindbergh
