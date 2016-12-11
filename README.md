# Ansible playbook for matrix/riot.im setup

This playbook sets up [Matrix](https://matrix.orG) and [Riot.im](https://riot.im) on a single server or two separate servers. The servers will request [Let's Ecrypt](https://letsencrypt.org) certificates for the hostnames assigned to them.

## Requirements

Ansible >= 2.2

## Usage

Add correct server names to the inventory file.
Set correct remote_user in ansible.cfg.

Set letsencrypt_email in group_vars/all/letsencrypt.yml
Set matrix and riot domains in group_vars/all/domains.yml
It's recommended to use different domains for these.

Run ansible-galaxy install -r requirements.yml

Run the site.yml playbook.

## User registration

By default user registration is disabled. You can enable it by setting matrix_enable_registration to True in group_vars/matrix_server/matrix.yml.

Note that by default captcha isn't enabled. By default using e-mail to register isn't supported. To enable it you would need to install and conifgure [Syndent](https://github.com/matrix-org/sydent).

You can also register new users directly into [Synapse](https://github.com/matrix-org/synapse#registering-a-user).

## Author

Kalle Happonen (https://github.com/kultsinuppeli/)
