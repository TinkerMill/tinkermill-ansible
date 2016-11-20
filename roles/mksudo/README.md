mksudo
=========

An Ansible role to add users to sudo.

Requirements
------------

Uses the following Core Ansible modules:
template

Role Variables
--------------

| Defaults | Description |
| -------- | ----------- |
| mksudo_users    | List defining sudoers. |

Override with variables at the group or host level for systems with special needs.  

See the "with_first_found" section of "Grant sudo for defined user(s)" for definition.

Dependencies
------------

Customize the defaults and files under ./templates before first use!

Example Playbook
----------------

    - hosts: gibsons
      roles:
         - { role: mksudo, mksudo_users: acidburn,cerealkiller,crashoverride,lordnikon,phantomphreak } #HACK THE PLANET!

License
-------

BSD

Author Information
------------------

> Chris Lindbergh
