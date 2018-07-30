# Ansible Cloud: Network role

An Ansible role for managing networks on the Cloud in an agnostic cloud provider way.

This role is part of the [ansible-cloud](https://github.com/redhat-cip/ansible-cloud) broader effort.

## Pre-requisites

Please refer to [ansible-cloud](https://github.com/redhat-cip/ansible-cloud) [README.md](https://github.com/redhat-cip/ansible-cloud/blob/master/README.md) to see how to configure your system the proper way for the provide you wish to use.


## Role Variables

| Variable name               | Required      | Default | Type   | Description                     |
|-----------------------------|---------------|---------|--------|---------------------------------|
| cloud_network_name          | True          | N/A     | String | Name of the network             |
| cloud_network_cidr          | True          | N/A     | Int    | CIDR of the network             |
| cloud_network_region        | (Amazon only) | N/A     | String | Region where the network is     |
| cloud_network_state         | False         | present | String | Should the network be present   |


## Example

```
---
- hosts: localhost
  vars:
    ansible_cloud_provider: amazon
  tasks:
    - name: Create network
      include_role:
        name: cloud-network
      vars:
        cloud_network_name: ansiblecloud-testnetwork
        cloud_network_size: 192.168.42.0/24
        cloud_network_region: nova
```


## License

Apache 2.0


## Authors Information

  - Ricardo Carrillo Cruz <ricarril@redhat.com>
  - Yanis Guenane <yguenane@redhat.com>
