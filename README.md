GoCD Server
===========

Installs GoCD (Go Continuous Delivery) https://www.go.cd

Requirements
------------

None

Role Variables
--------------

Available variables are listed below, defaults set in `defaults/main.yml`.

    gocd_server: false  # set to true to install server
    gocd_server_plugins_path: /var/lib/go-server/plugins/external
    gocd_server_plugins: []
    gocd_agent: false   # set to true to install agent

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: gocd-servers
      vars:
        gocd_server: true
        gocd_server_plugins:
          - https://github.com/gocd-contrib/docker-elastic-agents-plugin/releases/download/v3.0.0-245/docker-elastic-agents-3.0.0-245.jar
      roles:
         - role: dselders.gocd
           become: true

To install agents:

    - hosts: gocd-agents
      vars:
        gocd_agents: true
      roles:
        - role: dselders.gocd
          become: true

License
-------

BSD
