# Prometheus Playbook

This creates a Prometheus Instance on a blank server. It requires a PEM file to connect to the instance & perform the installation.

## Pre-requisites.

### Ansible CLI

This can be installed following instructions [here](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html). Or you can
install it with [pipenv](https://pipenv.pypa.io/en/latest/) with the [Pipfile](./Pipfile) file. This localizes the dependencies & avoids having them
globally installed.

### Server.

Ensure you have a running server that you can ssh into. This can be on cloud or OnPremise infrastructure

## Command(s)

1. Ensure on your running instance of your server, you have the key pair (usually a PEM file) to be able to connect to your running instance
2. Copy the sample `inventory.txt.sample` file onto `inventory.txt` file & change the values indicated in the file. Example is input the public IP of your server.

``` bash
cp inventory.txt.sample inventory.txt
```

3. Then run the command as below

``` bash
# if using the installed ansible-playbook dependency as is specified in the Pipfile
pipenv install
pipenv shell
ansible-playbook -i inventory.txt main.yml --private-key <PATH/TO/PEM_KEY>
```

> Command(s) to run to install prometheus on server