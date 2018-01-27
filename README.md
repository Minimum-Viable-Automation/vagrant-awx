# vagrant-awx
A simple AWX host for testing Ansible Tower locally.

## Accessing AWX

The host is configued to use the vagrant hostsupdater plugin to make the guest available at http://awx.local

Install the plugin with `vagrant plugin install vagrant-hostsupdater`

## Provisioning Notes

The installer uses the shell vagrant provisioner, so is pretty dumb when it comes to repovisoning and will just run the whole script again. As such, if you want to change the provisioning script `vagrant destroy; vagrant up` is likely to give a better result.
