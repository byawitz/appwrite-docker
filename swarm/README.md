# Swarm

Make sure to create a [decentralized](../decentralized) server first.

## Connect to your decentralized server.

```shell
# Setting the private key
mv sshfs /root/.ssh/id_rsa
chmod 600 /root/.ssh/id_rsa

# Updating
apt update
apt install sshfs

# Creating the base share folder
mkdir /home/share

# Add the mount, replace 10.0.0.15 with your decentralized server IP.
echo 'root@10.0.0.15:/home/share /home/share fuse.sshfs allow_other,x-systemd.automount' >> /etc/fstab

# Run mount manually
mount -a

# Check the listed
ls /home/share
```

## Deploy your Swarm stack

Put `.env` and `docker-compose.yml` inside the `/root/appwrite/` folder, adjust the environment variables inside the `.env` file. Then run

```shell
export $(grep -v '^#' .env | xargs) && docker stack config -c docker-compose.yml && docker stack deploy -c docker-compose.yml appwrite
```
