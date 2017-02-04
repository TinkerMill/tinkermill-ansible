# syslog-receiver

A role to configure RsyslogD as a TCP/UDP 514 syslog receiver.

## Requirements

Uses the following Core Ansible modules:
apt, service, template

## Role Variables

| Variable | Description | Default Value |
| -------- | ----------- | ------------- |
| syslog_receiver_remote_log_folder | Location of remote syslog folder | /var/log/remote |

## Dependencies

Depends on rsyslog being installed as a service.

## Example Playbook

Complete example:

    - hosts: servers
      roles:
         - { role: syslog-receiver, syslog_receiver_remote_log_folder: /var/log/remote }

## License

BSD

## Author Information

> Chris Lindbergh
