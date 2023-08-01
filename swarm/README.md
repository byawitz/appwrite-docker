In [stack](./stack) run

```shell
# Setting the private key
mv sshfs /root/.ssh/id_rsa
chmod 600 /root/.ssh/id_rsa

# Updating``
apt update
apt install sshfs

# Creating the base share folder
mkdir /home/share

# Add the mount, replace 10.0.0.15 with your decentralized server IP.
echo 'root@10.0.0.15:/home/share /home/share fuse.sshfs allow_other,x-systemd.automount' >>/etc/fstab

# Run mount manually
mount -a

# Check the listed
ls /home/share
```

## Use Ansible

Create Docker Swarm deployment of Appwrite by running one Ansible command!

Config files:

- [vars.yml](ansible/config/vars.yml) - Config Swap name & size, database details password
- [servers.yml](ansible/config/servers.yml) - Config the servers IP.

### Create passwords

To encrypt the database passwords, you'll need to use `ansible-vault` like so:

```shell
ansible-vault encrypt_string PASSWORD --ask-vault-pass
```

Replace `PASSWORD` with the desired one and set a password for the local vault.

### Run
Inside the [./ansible](./ansible) folder:

```shell
ansible-playbook appwrite.yml --ask-vault-pass

# In case you didn't encrypt the database passwords you can run
ansible-playbook appwrite.yml
```
