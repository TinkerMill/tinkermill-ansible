# tinkerpi

A role to configure a Raspberry Pi for general use at TinkerMill.

## Requirements

Uses the following Core Ansible modules:
lineinfile, locale_gen, service, shell

## Role Variables

None.

## Dependencies

None.

## Example Playbook

    - hosts: servers
      roles:
         - { role: tinkeraccess-server }

## License

BSD

## Author Information

> Chris Lindbergh
