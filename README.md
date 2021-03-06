# packer.boot2docker
HashiCorp Packer build for boot2docker persistance VM image for VirtualBox. Created virtual appliance booting from HDD and has persistant */opt* and */home* folders. Also installed extensions will not remove after reboot.

This VM is very small (~50Mb) and useful for developers, who wants to play with Docker.

####Requirements
* [Packer](https://www.vagrantup.com/) 
* [VirtualBox](https://www.virtualbox.org/)

# Usage
* `git clone https://github.com/ognivo777/packer.boot2docker.git`
* `cd packer.boot2docker`
* [Download latest release boot2docker.iso](https://github.com/boot2docker/boot2docker/releases/latest) and place near boot2docker.json
* Open boot2docker.json and fix "iso_checksum" using actual value from download page
* Run Packer: `packer build boot2docker.json`

When building complete **boot2docker_template.ova** appears in **output-virtualbox-iso** folder.

# Other options
**boot2docker_box.json** - same as boot2docker.json but creates **packer_virtualbox-iso_virtualbox.box** file.

# Example Vagrant file
This box uses NFS sync folder. So under windows you have to install vagrant plugin first:

`vagrant plugin install vagrant-winnfsd`

See https://github.com/winnfsd/vagrant-winnfsd for details.

For Vagrant exmaple with donwload and install Ansible see https://github.com/ognivo777/packer.boot2docker/tree/master/ansible.
