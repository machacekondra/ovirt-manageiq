Role Name
=========

This role downloads Manage IQ virtual appliance and deploys it into oVirt.

Requirements
------------

oVirt has to be 4.0.4 or higher and [ovirt-imageio](http://www.ovirt.org/develop/release-management/features/storage/image-upload/) must be installed and running.

Role Variables

--------------
```
 - ova_url - Define the URL where the Manage IQ OVA is stored
 - ovirt_user - Define the user to be used to access oVirt.
 - ovirt_url - Define the URL of the oVirt.
 - ovirt_ca - Define the path to the CA of the oVirt.
 - ovirt_password - Define password of the `ovirt_user`
 - vm_name - Define the name of the Manage IQ VM in oVirt.
 - vm_cluster - Define the cluster of the Manage IQ VM in oVirt.
 - vm_storage_domain - Define the storage domain of the Manage IQ VM in oVirt.
 - vm_cloud_init - Define cloud init dictionary to be passed to Manage IQ VM in oVirt.
```

Dependencies
------------

No.

Example Playbook
----------------

```yaml
    - name: Deploy ManageIQ to oVirt engine
      hosts: myovirt
      gather_facts: no
      vars:
        ovirt_url: https://myovirt/ovirt-engine/api
        ovirt_password: 123456
        vm_cloud_init:
          user_name: root
          root_password: 123456

      roles:
        - machacekondra.ovirt-manageiq
```

License
-------

GPLv2
