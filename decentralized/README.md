# Decentralized

## Create these folders:

```shell
mkdir /home/share
cd /home/share
mkdir mariadb redis cache uploads certificates functions builds config executor
```

## Create an SSH key

```shell
> ssh-keygen -t ed25519

cat sshfs.pub >> /root/.ssh/authorized_keys
```

_You'll use the private key for either the `horizontal` or the `swarm` method._

## Start docker compose

Put `.env` and `docker-compose.yml` inside the `/root/databases/` folder, adjust the environment variables inside the `.env` file. Then run

```shell
docker-compose up -d
```
