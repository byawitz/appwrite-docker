# Vertical scaling

## Use Ansible

Create Appwrite server using Ansible.

Config files:

- [vars.yml](ansible/config/vars.yml) - Config Swap name & size.
- [servers.yml](ansible/config/servers.yml) - Config for the server IP.

### Run

```shell
ansible-playbook appwrite.yml
```
