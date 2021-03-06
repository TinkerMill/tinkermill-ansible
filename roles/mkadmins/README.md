# mkadmins

An Ansible role to create one (or more) administrator accounts, including 'dot rc files' and groups if specified.

## Requirements

Uses the following Core Ansible modules:
group, template, user

## Role Variables

| Variable | Description | Default Value |
| -------- | ----------- | ------------- |
| mkadmins_users |  Dictionary defining users. | (several users) |
| mkadmins_rc_files | 'dot rc files' to place for new users. | (several files) |

Override with variables at the group or host level for systems with special needs, for example a host that needs a second .screenrc file so it can master other screen sessions.

Simple example with one user:

    mkadmins_users:
      merlin:
        state: present
        name: Merlin the Wizard
        shell: /bin/bash
        password: $6$rounds=40000$ThisIsNotTheGreatestPasswordInTheWorld,NoThisIsJustTheHash
    mkadmins_rc_files:
      - name: merlin
        group:
        files:
          - .bashrc
          - .screenrc
          - .vimrc

Generate useful password hashes with this command on any system with the "python-passlib" package:

> $ python -c "from passlib.hash import sha512_crypt; import getpass; print sha512_crypt.encrypt(getpass.getpass())"

## Dependencies

Customize **./defaults/main.yml** and **./templates/*.j2** before first use!

## Example Playbook

    - hosts: gibsons
      roles:
         - { role: mkadmins }

## License

BSD

## Author Information

> Chris Lindbergh

