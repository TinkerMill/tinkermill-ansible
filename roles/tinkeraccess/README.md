# tinkeraccess

A role to configure a Raspberry Pi as a server or client for the TinkerAccess system.

## Requirements

Uses the following Core Ansible modules:
git, service, shell, template

## Role Variables

| Variable | Description | Default Value |
| -------- | ----------- | ------------- |
| tinkeraccess_repo_dest | Location on the RPi to place the git repo | /root/tinkerAccess |
| tinkeraccess_repo_source | URL to pull git repo from | https://github.com/TinkerMill/tinkerAccess.git |
| tinkeraccess_server_enabled | If True, enable tinkerAccess server | False |
| tinkeraccess_client_enabled | If True, enable tinkerAccess client | True | 
| tinkeraccess_client | Name of tinkerAccess client service | tinker-access-client |
| tinkeraccess_server | Name of tinkerAccess server service | tinkerserver |
| tinkeraccess_log_level | Integer level of logging | 40 |
| tinkeraccess_reboot_on_error | If True, reboot the supported RPi when any unhandled error is encountered | False |
| tinkeraccess_reboot_delay | Integer number of seconds to wait before rebooting | 300 |
| tinkeraccess_auto_update | If True, update tinkerAccess automatically | False |
| tinkeraccess_auto_update_interval | Integer number of minutes to wait betwen auto update checks | 5 |
| tinkeraccess_device_id | Unique integer identifier for a client, as configure in the tinker-access-client | 0 |
| tinkeraccess_logout_coast_time | Integer number of seconds to wait for the physical machine to stop after power has been disabled. (i.e. a blade to stop spinning etc...) | 0 |
| tinkeraccess_server_address | The tinker-access-server's api address | http://localhost:5000 |

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
