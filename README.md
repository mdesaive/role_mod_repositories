role_mod_repositories
=========

Sets up Linux Distribution specific repositories.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

Expects a list of repositories in either "role_mod_repositories_yum_repos" or "role_mod_repositories_deb_repos" 

    - role_mod_repositories_yum_repos:
        - name: CloudStack-ShapeBlue
          description: "ShapeBlue CloudStack Repository."          
          file: "CloudStack-ShapeBlue"          
          baseurl: "http://packages.shapeblue.com/cloudstack/upstream/centos7/{{ role_hv_kvm_acs_agent_acs_version }}"
          gpgcheck: "yes"
          gpgkey: "http://packages.shapeblue.com/release.asc"
          enabled: "yes"

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

The role is intended to be called from other roles as a module:

    - name: Create Repositories
      import_role:
        name: role_mod_repositories
      vars:
        - role_mod_repositories_yum_repos:
            - name: CloudStack-ShapeBlue
              description: "ShapeBlue CloudStack Repository."
              file: "CloudStack-ShapeBlue"
              baseurl: "http://packages.shapeblue.com/cloudstack/upstream/centos7/{{ role_hv_kvm_acs_agent_acs_version }}"
              gpgcheck: "yes"
              gpgkey: "http://packages.shapeblue.com/release.asc"
              enabled: "yes"

License
-------

GNU General Public License v3.0

Author Information
------------------

Melanie Desaive - m.desaive@mailbox.org
