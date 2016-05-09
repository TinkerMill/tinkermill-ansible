install-omd
=========

A role to install OMD and set up an initial site.

Requirements
------------

None.

Role Variables
--------------

omd_site: hq

Dependencies
------------

None.

Example Playbook
----------------

Complete example:

    - hosts: servers
      roles:
         - { role: install-omd, omd_site: test }

License
-------

BSD

Author Information
------------------

> Chris Lindbergh
