php_fpm
========

Install latest PHP fpm version in DotDeb repository

Requirements
------------

Debian Wheezy with the package python-pycurl and python-software-properties installed.

Role Variables
--------------

There are as many role variables as PHP.ini variables. All of them can be set, but the defaults
are adjusted according to [iniscan](https://github.com/psecio/iniscan) security best practices.

This package depends on f500.php7, and all the php_* variables are used as defaults for the php_fpm* variables.

Dependencies
------------

Depends on f500.php.

Example Playbook
-------------------------

    - hosts: servers
      roles:
         - { role: f500.php7_fpm, php_fpm_error_reporting: "E_ALL" }

      OR, if you prefer TCP over Unix socket:

        - { 
            role: f500.php7_fpm, 
                php_fpm_error_reporting: "E_ALL",
                php_fpm_listen: "127.0.0.1:9100",
                php_fpm_listen_allowed_clients: "127.0.0.1, 127.0.1.1",
        }

License
-------

LGPL

Author Information
------------------

Jasper N. Brouwer, jasper@nerdsweide.nl

Ramon de la Fuente, ramon@delafuente.nl
