# install-omd

A role to install OMD/Check_MK RAW and set up an initial site.

## Requirements

Uses the following Core Ansible modules:
apt, command, get_url 

## Role Variables

| Variable | Description | Default Value |
| -------- | ----------- | ------------- |
| omd_site | Name of initial OMD/Check_MK RAW 'site' to provision | hq |

## Dependencies

Depends on APT/Debian support.

## Example Playbook

Complete example:

    - hosts: servers
      roles:
         - { role: install-omd, omd_site: test }

## License

BSD

## Author Information

> Chris Lindbergh
