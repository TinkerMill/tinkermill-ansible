install-cmkagent
=========

A role to configure a 'cmkagent' user, then configure it for sudo, copy over the Check_MK agent, and so on.

Requirements
------------

None.

Role Variables
--------------

count_users_warn: 10
count_users_crit: 15

count_zombie_procs_warn: 5
count_zombie_procs_crit: 10

local_checks:
  - count_users
  - count_zombie_procs

Dependencies
------------

None.

Example Playbook
----------------

Simple example with one override:

    - hosts: servers
      roles:
         - { role: install-cmkagent, count_users_warn: 20, count_zombie_procs_crit: 30 }

License
-------

BSD

Author Information
------------------

> Chris Lindbergh
