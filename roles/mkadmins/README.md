mkadmins
=========

An Ansible role to create one (or more) administrator accounts, including 'dot rc files' and groups if specified.

Requirements
------------

Uses the following Core Ansible modules:
group, user, template

Role Variables
--------------

| Defaults   | Description |
| ---------- | ----------- |
| mkadmins_users |  Dictionary defining users. |
| mkadmins_rc_files | 'dot rc files' to place for new users. |

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

Dependencies
------------

Customize **./defaults/main.yml** and **./templates/*.j2** before first use!

Example Playbook
----------------

    - hosts: gibsons
      roles:
         - { role: mkadmins }

License
-------

BSD

Author Information
------------------

> Chris Lindbergh
