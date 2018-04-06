Jupyterlabhub
=========

Performs a minimal install of jupyterhub, the lab extension, GitHub Oauth, a letsencrypt cert, and nginx to perform HTTPS forwarding,

Requirements
------------

No other requirements are needed.

Role Variables
--------------

There are only two variables, the hostname that is used in the cert/nginx config, and the email to be used to register the certificate. See the example for naming.

Dependencies
------------

No other dependencies are needed.

Example Playbook
----------------

```yaml
    - hosts: dev
      tasks:
      - include_role:
           name: jupyterlabhub
        vars:
          cert_email: example@example.com
          hostname: example.com
          jh_admin_users:
            - dbd # These are the github usernames that will also be local accounts
          jh_users:
            - dbd
          git_client_id: your_github_oauth2_client_id
          git_client_secret: your_github_oauth2_client_secret
```

License
-------

BSD

Author Information
------------------

Derek Daniels - dbdaniel@mtu.edu
