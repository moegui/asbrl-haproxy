ASBRL-HAProxy
=========

Deploy HAProxy

Requirements
------------

Need to have Docker engine installed.

Role Variables
--------------
 - HA_CONFIG: local path to a haproxy.cfg file to use for HA proxy
 - HA_PORT: Port to map to HA proxy
 - HA_LOG: global
 - HA_MODE: tcp
 - HA_RETRIES: 2
 - HA_TIMEOUT_CLIENT: 30m
 - HA_TIMEOUT_CONNECT: 4s
 - HA_TIMEOUT_SERVER: 30m
 - HA_TIMEOUT_CHECK: 5s

Dependencies
------------

None

Example Playbook
----------------

    ---
    - name: example
      gather_facts: true
      hosts: "haproxy"
      order: sorted

      tasks:
        - name: Run ha proxy
          include_role:
            name: asbrl-haproxy
          vars:
            HA_CONFIG: /mnt/c/git/moegui/asbrl/asbrl-haproxy/test/haproxy.cfg
            HA_PORT: '8080'

License
-------

BSD

Author Information
------------------

Moegui.com