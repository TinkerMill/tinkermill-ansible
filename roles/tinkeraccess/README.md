# tinkeraccess

A role to configure a Raspberry Pi so it can act as a server for the TinkerAccess system.

## Requirements

Uses the following Core Ansible modules:
git, service, shell

## Role Variables

| Variable | Description | Default Value |
| -------- | ----------- | ------------- |
| tinkeraccess_repo_dest | Location on the RPi to place the git repo | /root/tinkerAccess |
| tinkeraccess_repo_source | URL to pull git repo from | https://github.com/TinkerMill/tinkerAccess.git |
| tinkeraccess_server_enabled | Switch to enable/disable tinkerAccess client | False |
| tinkeraccess_client_enabled | Switch to enable/disable tinkerAccess server | True | 
| tinkeraccess_client | Name of tinkerAccess client | tinker-access-client |
| tinkeraccess_server | Name of tinkerAccess server | tinkerserver |

## Dependencies

None.

## Example Playbook

    - hosts: servers
      roles:
         - { role: tinkeraccess }

## License

BSD

## Author Information

> Chris Lindbergh
