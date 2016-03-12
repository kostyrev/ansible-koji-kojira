koji-kojira
=========

 This role installs and configures the kojira.

This is one of the koji- roles which configures the whole koji stack.

Roles are:

 * [koji-ca](https://galaxy.ansible.com/kostyrevaa/koji-ca)
 * [koji-db](https://galaxy.ansible.com/kostyrevaa/koji-db)
 * [koji-client](https://galaxy.ansible.com/kostyrevaa/koji-client)
 * [koji-hub](https://galaxy.ansible.com/kostyrevaa/koji-hub)
 * [koji-web](https://galaxy.ansible.com/kostyrevaa/koji-web)
 * [koji-kojira](https://galaxy.ansible.com/kostyrevaa/koji-kojira)
 * [koji-builder](https://galaxy.ansible.com/kostyrevaa/koji-builder)

For example of all-in-one setup go to https://github.com/kostyrevaa/ansible-koji-infra

Role Variables
--------------

There are some variables in the default/main.yml which can (or needs to) be changed/overriden:

* `koji_kojira_user`: Same as in cert's CN. Default is kojira.

* `koji_kojira_hub_server`: This is the url of koji hub. Default uses var from koji-builder.

* `koji_kojira_topdir`: This is topdir of the koji. Default is /mnt/koji.

* `koji_builder_topurl`: This is the url of kojifiles. Default uses hostvars discover.

* `koji_kojira_cert`: This is the client certificate of kojira user. Default is /etc/pki/koji/pems/kojira.pem.

* `koji_kojira_ca`: This is the certificate of the CA that issued the client certificate. Default is /etc/pki/koji/koji_ca_cert.crt.

* `koji_kojira_serverca`: This is the certificate of the CA that issued the HTTP server certificate. Default is /etc/pki/koji/koji_ca_cert.crt.

* `koji_kojira_grant_repo`: Should this role attempt to execute shell command that grants kojira repo permission. If this is a all-in-one setup put true. Default is false.

* `koji_kojira_issue_cert`: Should this role attempt to issue cert for kojira. If this is a all-in-one setup set it to true. Default is false.


Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: koji_hub
      roles:
         - kostyrevaa.koji-kojira

License
-------

GPLv3

Author Information
------------------

Send your suggestions and pull requests to https://github.com/kostyrevaa/ansible-koji-kojira.  
When send PR make sure your changes are backward-compatible.  
You may test your changes to role with https://github.com/kostyrevaa/ansible-koji-infra
