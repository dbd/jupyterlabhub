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

    - hosts: servers
      roles:
         - { role: Jupyterlabhub, hostname: example.com, cert_email: webmaster@example.com }

License
-------

BSD

Author Information
------------------

Derek Daniels - dbdaniel@mtu.edu
