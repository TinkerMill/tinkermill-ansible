fwd-syslog
=========

A simple role to configure RsyslogD so that it forwards syslog messages to a defined server.

Requirements
------------

None.

Role Variables
--------------

Set "syslog_server" to your local syslog receiver system.  The default is set to "localhost" which is better than nothing! :)

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: fwd-syslog, syslog_server: archivist-01 }

License
-------

BSD

Author Information
------------------

> Chris Lindbergh
