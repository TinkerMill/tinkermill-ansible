# install-omd

A role to install OMD/Check_MK RAW and set up an initial site.

## Requirements

Uses the following Core Ansible modules:
apt, command, get_url 

## Role Variables

| Variable | Description | Default Value |
| -------- | ----------- | ------------- |
| install_omd_version | Version of Check_MK RAW Edition to install | `1.4.0p8` |
| install_omd_source_url | URL of source package | `https://mathias-kettner.de/support/{{ install_omd_version }}/check-mk-raw-{{ install_omd_version }}_0.{{ ansible_distribution_release }}_amd64.deb` |
| install_omd_deb | Absolute path of downloaded source package | `/opt/check-mk-raw-{{ install_omd_version }}_0.{{ ansible_distribution_release }}_amd64.deb` |
| install_omd_site | Name of Check_MK RAW Edition 'site' to provision | `test` |

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
