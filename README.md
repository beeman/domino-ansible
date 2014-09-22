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

## Defaults

The default installation of the Domino data directory goed to `/local/notesdata`. The installer will be downloaded from the provider URL and unpacked in `/local/installer`. 

Both paths can be mounted to existing locations, the script will than skip downloading and/or installing the default userdata. 

The domino server runs under the user/group/uid `domino/domino/10000`.

## Credentials

To login on the Domino environment you need to use the following credentials

    username   : admin/dominodev
    password   : dominodev
    id file    : /local/notesdata/admin.id
