Package downloader
=========

This role allows downloading ISO and setup bundles for most common RH products. It uses the API token to interact with Red Hat API.

Requirements
------------

The role doesn't have specific requirements

Role Variables
--------------

The only required values are:
  rh_api_offline_token - The Red Hat offline token that can be retrieved (here)[https://access.redhat.com/management/api]

  rh_product_checksum - The checksum of the package to download. They can be retrieved (here)[https://access.redhat.com/downloads/] or you can use some of the common one under *vars* folder


Dependencies
------------

No dependencies

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - role: role-package-downloader
          vars:
            rh_api_offline_token: <YOUR TOKEN HERE>
            rh_product_checksum: "{{ rhel.86.binary }}"

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
