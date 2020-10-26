# ansible-nso

The ansible-nso project provides an Ansible collection for managing and automating your Cisco NSO environment. It consists of a set of modules and roles for performing tasks in NSO.

This collection has been tested and supports version 5.3+ of NSO.

*Note: This collection is not compatible with versions of Ansible before v2.9.

## Requirements
Ansible v2.9 or newer

## Install
Ansible must be installed
```
sudo pip install ansible
```

Install the collection
```
ansible-galaxy collection install cisco.nso
```
## Use
Once the collection is installed, you can use it in a playbook by specifying the full namespace path to the module, plugin and/or role.

```yaml
- hosts: nso
  gather_facts: no

  tasks:
    - name: Create L3VPN
      cisco.nso.nso_config:
        url: http://localhost:8080/jsonrpc
        username: nso_username
        password: nso_password
        data:
        l3vpn:vpn:
            l3vpn:
            - name: company
            route-distinguisher: 999
            endpoint:
            - id: branch-office1
                ce-device: ce6
                ce-interface: GigabitEthernet0/12
                ip-network: 10.10.1.0/24
                bandwidth: 12000000
                as-number: 65101
            - id: branch-office2
                ce-device: ce1
                ce-interface: GigabitEthernet0/11
                ip-network: 10.7.7.0/24
                bandwidth: 6000000
                as-number: 65102
            - id: branch-office3
                __state: absent
            __state: in-sync
```

## Update
Getting the latest/nightly collection build

### First Approach
Clone the ansible-nso repository.
```
git clone https://github.com/CiscoDevNet/ansible-nso.git
```

Go to the ansible-nso directory
```
cd ansible-nso
```

Pull the latest master on your NSO
```
git pull origin master
```

Build and Install a collection from source
```
ansible-galaxy collection build --force
ansible-galaxy collection install cisco-nso-* --force
```

### See Also:

* [Ansible Using collections](https://docs.ansible.com/ansible/latest/user_guide/collections_using.html) for more details.

## Contributing to this collection

Ongoing development efforts and contributions to this collection are tracked as issues in this repository.

We welcome community contributions to this collection. If you find problems, need an enhancement or need a new module, please open an issue or create a PR against the [Cisco NSO collection repository](https://github.com/CiscoDevNet/ansible-nso/issues).