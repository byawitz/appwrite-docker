# Scaling Appwrite

## ⚡ Introduction

In this repo, you'll find all the necessary files needed for deploying Appwrite:

- Using a single server.
- Using multiple servers with a decentralized database & storage.
- Using Docker Swarm with a decentralized database & storage.

### Deployment types

| Technique                  | Description                                                            |
|----------------------------|------------------------------------------------------------------------|
| [Vertical](./vertical)     | Scale your Appwrite up and down using single server                    |
| [Horizontal](./horizontal) | Scale your Appwrite left and right using multiple **services** servers |
| [Swarm](./swarm)           | Scale your Appwrite using multiple docker **swarm** servers.           |

### Addon

| Name                             | Description                                                                                |
|----------------------------------|--------------------------------------------------------------------------------------------|
| [Decentralized](./decentralized) | Single decentralized storage and databases server to be used with `Horizontal` and `Swarm` |

## 🎩 Using ansible

Any deployments contain fully working Ansible scripts, so you can deploy your Appwrite infrastructure with a single command!

### Config files:

Inside each Ansible sub folder, you'll find two files inside the `config` folder

- `vars.yml` - List of variable you can customize prior to the deployment.
- `servers.yml` - List of all your servers and groupds.

All you need to do is to update the variables inside the `vars.yml` file, and set each server IP. Notice that in `Horizontal` and `Swarm` the separation of the
servers into groups is done for you.

### Encrypt variables

To encrypt the database passwords, or any variables inside the `vars.yml` file, you can use `ansible-vault` like so:

```shell
ansible-vault encrypt_string PASSWORD --ask-vault-pass
```

Replace `PASSWORD` with the desired value and set a password for the local vault.

### Run

Inside the `ansible` folder:

```shell
# In case you did encrypt some vars
ansible-playbook appwrite.yml --ask-vault-pass

# In case you didn't encrypt any vars
ansible-playbook appwrite.yml
```

Grab a coffee ☕ and watch your infrastructure come to life.

## 🧙‍♂️ Looking for more?

Check my official DevOps Book in [English](https://book.appread.io/) or in [Hebrew](https://book.appread.io/he/). 
