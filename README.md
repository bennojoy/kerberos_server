kerberos_server
========

This role helps in installing Kerberos server on the target host. 
The playbook deploys the kerberos server and creates a new realm as specified in the paramter, it also creates a default admin user which can be used for managing this kerberos server. The default admin name can be specified via "kadmin_user" and password via "kadmin_pass"

Requirements
------------

This role requires ansible 1.4 or higher and platform requirements are listed in the metadata file

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows:

    kerberos_server_realm_name: EXAMPLE.COM                           # The realm name for the kerneros server
    kerberos_server_kdc_port: 88                                      # The port in which kdc should listen
    kerberos_server_master_db_pass: foobar                            # Password for the master kerberos database
    kerberos_server_kadmin_pass: foobar                               # Password for the kerberos admin
    kerberos_server_kadmin_user: benz                                 # Username for the kerberos server

Example
-------

Following is an example which deploys are kerberos server with Realm as BENNO.COM and a admin user "root" and password "foobar"

    - hosts: all
      roles:
        - {role: kerberos_server, kerberos_server_realm_name: "BENNO.COM", 
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

Benno Joy

