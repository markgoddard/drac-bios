DRAC BIOS
=========

This role supports configuration of BIOS settings on Dell machines with an
iDRAC card.

[![Build Status](https://travis-ci.org/markgoddard/drac-bios.svg?branch=master)](https://travis-ci.org/markgoddard/drac-bios)
[![Ansible Galaxy](https://img.shields.io/badge/role-markgoddard.drac--bios-blue.svg)](https://galaxy.ansible.com/markgoddard/drac-bios/)

Requirements
------------

The role provides a module, `drac_bios`, that is dependent upon the
`python-dracclient` module. This must be installed in order for this module
to function correctly.

Role Variables
--------------

The following variables may be set for this role:

`drac_address`: The address to use when communicating with the DRAC.
`drac_username`: The username to use when communicating with the DRAC.
`drac_password`: The password to use when communicating with the DRAC.
`drac_bios_config`: Dict mapping BIOS configuration names to their desired values.
`drac_reboot`: Whether to reboot the node once BIOS settings have been applied.
`drac_timeout`: Time in seconds to wait for pending operations to complete. 0 means to wait forever.
`drac_interval`: Time in seconds between polling for operations to complete.

Dependencies
------------

None

Example Playbook
----------------

This role may be used as follows:

    - hosts: dell-servers
      roles:
        - role: markgoddard.drac-bios
          drac_address: 1.2.3.4
          drac_username: foo
          drac_password: bar
          drac_bios_config:
            NumLock: 'On' 
            SysProfile: 'PerfOptimized'

License
-------

BSD

Author Information
------------------

- Authors: Mark Goddard & Stig Telfer
- Company: StackHPC Ltd
- Website: https://stackhpc.com
