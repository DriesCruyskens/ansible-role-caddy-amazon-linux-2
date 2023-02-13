Caddy webserver role for Amazon Linux 2
=========

Installing Caddy on Amazon Linux 2 wasn't so straight forward as I had hoped for. To make it easier for other people I made this role which:

- Enables yum-plugin-copr
- Enables @caddy/caddy copr repo
- Installs Caddy
- Transfers basic reverse localhost proxy Caddyfile with variables:
  ```caddyfile
  # Caddyfile
  {{ domain }} {
        reverse_proxy localhost:{{ reverse_proxy_port }}
  }
  ```
- Starts and enables the Caddy service (which doesn't happen automatically on this distro)

If you need more customisability, copy and adjust the source code or just overwrite the template with your own.


Role Variables and their defaults
--------------

- domain: ":80"
- reverse_proxy_port: 3000
  
  
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

Requirements
------------

/


Dependencies
------------

/


License
-------

BSD
