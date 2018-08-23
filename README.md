kerberos_server
========

[![Build Status](https://travis-ci.com/ultratendency/kerberos_server.svg?branch=master)](https://travis-ci.com/ultratendency/kerberos_server)

This role helps in installing a KDC on the target host, initially forked from the repository of Benno Joy. 
The playbook deploys a KDC and creates a new realm as specified in the parameter, it also creates a default admin user
which can be used for managing this kerberos server. The default admin name can be specified via "kerberos_server_kadmin_user"
and password via "kerberos_server_kadmin_pass". Additionally a user called "cloudera-scm" is created to be used by
Cloudera Manager.

Requirements
------------

This role requires Ansible 1.4 or higher and platform requirements are listed in the metadata file.

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows:

    kerberos_server_realm_name: EXAMPLE.COM         # The realm name for the kerberos server
    kerberos_server_kdc_port: 88                    # The port in which kdc should listen
    kerberos_server_master_db_pass: foobar          # Password for the master kerberos database
    kerberos_server_kadmin_pass: foobar             # Password for the kerberos admin
    kerberos_server_kadmin_user: test               # Username for the kerberos server

Example
-------

Following is an example which deploys are kerberos server with Realm as EXAMPLE.COM and a admin user "root" and password "foobar"

    - hosts: all
      roles:
        - {role: kerberos_server, kerberos_server_realm_name: "EXAMPLE.COM", 
                            kerberos_server_kadmin_user: "root", 
                            kerberos_server_kadmin_pass: "foobar" }


Dependencies
------------

None

License
-------

BSD

Author Information
------------------

Matthias Baumann & Jan Hentschel
