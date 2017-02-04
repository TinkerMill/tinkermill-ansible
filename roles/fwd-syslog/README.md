# fwd-syslog

A simple role to configure RsyslogD so that it forwards syslog messages to a defined server.

## Requirements

Uses the following Core Ansible modules:
template, service

## Role Variables

| Variable | Description | Default Value |
| -------- | ----------- | ------------- |
| syslog_server | Your local syslog receiver system | localhost |

## Dependencies

Depends on rsyslog being installed as a service.

## Example Playbook

    - hosts: servers
      roles:
         - { role: fwd-syslog, syslog_server: archivist-01 }

## License

BSD

## Author Information

> Chris Lindbergh
