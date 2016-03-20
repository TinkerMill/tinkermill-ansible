syslog-receiver
=========

A role to configure RsyslogD as a TCP/UDP 514 syslog receiver.

Requirements
------------

None.

Role Variables
--------------

syslog_receiver_remote_log_folder: /var/log/remote

Dependencies
------------

None.

Example Playbook
----------------

Complete example:

    - hosts: servers
      roles:
         - { role: syslog-receiver, syslog_receiver_remote_log_folder: /var/log/remote }

License
-------

BSD

Author Information
------------------

> Chris Lindbergh
