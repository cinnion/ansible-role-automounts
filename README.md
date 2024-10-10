# Role Name: automounts

This role provisions a set of NFS automounts for autofs.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    nfs_server: "nas.example.com"

Name of the NFS server.

    nfs_home_server: "nas.example.com"

Name of the NFS server providing home directories.

    nfs_home_path: "/homes/"

Path of the home directories on the NFS server.


    nfs_home_fstype: "nfs"

Type of NFS automount to use for home directories.
Recommended values: `nfs` or `nfs4`

## Dependencies

None.

## Example Playbook

    - hosts: automounters
      roles:
        - automount

    - hosts: automounter
      roles:
         - { role: automounts, nfs_home_fstype: nfs4 }

## License

BSD

## Author Information

This role was created in 2019 by [Douglas Needham](https://www.ka8zrt.com/).
