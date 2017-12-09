Gluster volume management
==========================

Creates gluster volume & bricks

Requirements
------------

Gluster server (https://github.com/leucos/ansible-gluster.git)

Role Variables
--------------

TBD

Dependencies
------------

You need to open ports for communication among brick servers.
You can use https://github.com/leucos/ansible-ferm.git for this:

  - role: ansible-ferm
    ferm_input_group_list:
      - type: 'dport_accept'
        dport: [ '49152', '49153', '49154', '49155' ]
        saddr: '{{ play_hosts }}'
        weight: '50'
        filename: 'gluster_bricks_accept'

License
-------

MIT

Author Information
------------------

@leucos
