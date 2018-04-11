Jupyterlabhub
=========

Performs a minimal install of jupyterhub, the lab extension, GitHub Oauth, a letsencrypt cert, and nginx to perform HTTPS forwarding,

Requirements
------------

You must create a new [GitHub OAuth App](https://github.com/settings/developers). This is used for the oauthenticator.

Role Variables
--------------
```yaml
cert_email:
  # Email to used for certificate
hostname:
  # Hostname of server. Used for cert and nginx config
jh_admin_users:
  -
  # List of github users that will have admin rights to jupyterhub config/kernels
jh_users:
  -
  # list of github users that will be able to login to server
git_client_id:
  # Created from GitHub OAuth App
git_client_secret:
  # Created from GitHub OAuth App
extra_pip_packages:
  -
  # List of additional pip packages to install for all users
```


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
