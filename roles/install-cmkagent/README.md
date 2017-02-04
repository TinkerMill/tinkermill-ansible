# install-cmkagent

A role to configure a 'cmkagent' user, then configure it for sudo, copy over the Check_MK agent, and so on.

## Requirements

Uses the following Core Ansible modules:
copy, file, group, template, user

Requires sudo on the remote server.

## Role Variables

| Variable | Description | Default Value |
| -------- | ----------- | ------------- |
| count_users_warn | Logged in users, warning threshold | 10 |
| count_users_crit | Logged in users, critical threshold | 15 |
| count_zombie_procs_warn | Zombie processes, warning threshold | 5 |
| count_zombie_procs_crit | Zombie processes, critical threshold | 10 |
| local_checks | Dictionary containing active local checks | count_users, count_zombie_procs |

## Dependencies

None.

## Example Playbook

Simple example with one override:

    - hosts: servers
      roles:
         - { role: install-cmkagent, count_users_warn: 20, count_zombie_procs_crit: 30 }

## License

BSD

## Author Information

> Chris Lindbergh
