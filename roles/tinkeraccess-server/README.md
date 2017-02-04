# tinkeraccess-server

A role to configure a Raspberry Pi so it can act as a server for the TinkerAccess system.

## Requirements

Uses the following Core Ansible modules:
git, lineinfile, locale_gen, service, shell

## Role Variables

| Variable | Description | Default Value |
| -------- | ----------- | ------------- |
| tinkeraccess_repo_dest | Location on the RPi to place the git repo | /root/tinkerAccess |
| tinkeraccess_repo_source | URL to pull git repo from | https://github.com/TinkerMill/tinkerAccess.git |

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
