# Package downloader

This role allows downloading ISO and setup bundles for most common RH products. It uses the API token to interact with Red Hat API.

The package is downloaded by default in the playbook execution folder. It can be customized via _rh_product_path_ and _rh_product_filename_ variables.

## Requirements

The role doesn't have specific requirements

## Role Variables

The only required values are:

| Name                 | Description                                                                                      | Default                                                     |
| -------------------- | ------------------------------------------------------------------------------------------------ | ----------------------------------------------------------- |
| rh_api_offline_token | The Red Hat offline token that can be retrieved [here](https://access.redhat.com/management/api) | Mandatory                                                   |
| rh_product_name      | The product you need to download (it can be 'rhel8', 'rhel9', 'aap2_containerized')      | No default, mandatory if rh_product_checksum is not defined |
| rh_product_path      | The location to save the file to                                                                 | Defaults to /root                                           |
| rh_product_filename  | The name of the package if different from the original one                                       | Defaults to the iso/tar name from RH website                |
| rh_product_checksum  | The checksum of the file to download                                                             | No default, mandatory if rh_product_name is not defined     |

## Output

The role will provide a fact **rh_package_path** that can be used for subsequent elaboration (extraction/copy/etc)

## Dependencies

No dependencies

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
        - role: role-package-downloader
          vars:
            rh_api_offline_token: <YOUR TOKEN HERE>
            rh_product_name: <YOUR PRODUCT HERE - aap2/rhel8/rhel9>
            rh_product_path: <YOUR PATH HERE>
            rh_product_filename: <YOUR PRODUCT FILENAME HERE - ansible-automation-platform-containerized-setup-{{ controller_version }}.tar.gz>
            rh_product_checksum: <YOUR PRODUCT CHECKSUM HERE - 39c5f84421585fe0171fc0532d3507d195fc32bf5b74e53bfd4e9bcca7a0fcd0 >

## License

BSD

## Author Information

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
