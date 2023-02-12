# Caddy webserver role for Amazon Linux 2
=========

Installing Caddy on Amazon Linux 2 wasn't so straight forward as I had hoped for. To make it easier for other people I made this role which:

- Enables required yum repo
- Installs Caddy
- Transfers basic reverse proxy Caddyfile with variables:
  - DOMAIN
  - REVERSE_PROXY_PORT
- Starts and enables the Caddy service (which doesn't happen automatically on this distro)

If you need more customisability, copy and adjust the source code or just overwrite the template with your own.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

```yaml
- become: yes
  hosts: all
  name: Install Caddy on Amazon Linux 2
  roles: 
    - role: caddy_amazon_linux_2
      vars:
        - domain: "example.com"
        - reverse_proxy_port: 3000
```

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
