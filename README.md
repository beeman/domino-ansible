# domino-ansible

Ansible script that installs a Domino server on CentOS 6 

## Usage

First you need to [install Ansible](http://docs.ansible.com/intro_installation.html) on one of your machines (for instance your laptop or a server used for deployments).

Next clone this repository and enter the directory you cloned:

    $ git clone https://github.com/beeman/domino-ansible.git
    $ cd domino-ansible

Now edit the `hosts` file to match the machine(s) you want to deploy to.

    [domino]
    your.hostname.here.net
    another.host.org

Next run the `ansible-playbook` command to apply the configuration to these hosts.

    $ ansible-playbook -i hosts install.yml

## Configuration

You can change some configuration parameters in the file `roles/domino-server/vars/main.yml`. 

## Credentials

To login on the Domino environment you need to use the following credentials

    username   : admin/dominodev
    password   : dominodev
    id file    : /local/notesdata/admin.id
