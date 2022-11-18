Package downloader
=========

This role allows downloading ISO and setup bundles for most common RH products. It uses the API token to interact with Red Hat API.

The package is downloaded by default in the playbook execution folder. It can be customized via *rh_product_path* and *rh_product_filename* variables.

Requirements
------------

The role doesn't have specific requirements

Role Variables
--------------

The only required values are:

| Name | Description | Default |
| ------------ | ------------ | ------------ |
| rh_api_offline_token | The Red Hat offline token that can be retrieved [here](https://access.redhat.com/management/api) | Mandatory |
| rh_product_name | The product you need to download (it can be 'rhel8', 'rhel9', 'aap2') | No default, mandatory |
| rh_product_path | The location to save the file to | Playbook directory - {{ playbook_dir }} |
| rh_product_filename | The name of the package if different from the original one | Defaults to the iso/tar name from RH website |

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
            rh_product_name: <YOUR PRODUCT HERE - aap2/rhel8/rhel9>
            rh_product_path: <YOUR PATH HERE>
            rh_product_filename: <YOUR PRODUCT FILENAME HERE - ansible-automation-platform-setup-{{ controller_version }}.tar.gz>
License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
