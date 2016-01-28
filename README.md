# Packer template for Alpine Linux

Build a machine image for [Alpine linux](http://www.alpinelinux.org) using [Packer](https://www.packer.io).

    packer build alpine.json

When Alpine is first booted it runs from memory and does not have any network connectivity. As a result all of the boot and install commands have to be sent over VNC.

The boot command will install to disk, configure network, and setup a user for use with SSH. Note that the root account is not accessible over SSH so you must use the other user account (default `vagrant` password `vagrant`. You can customize this login

    packer build -var=ssh_username=youruser -var=ssh_password=yourpassword

Aside from that the installation is super bare-bones. Feel free to add your own stuff by way of provisioners.

## TODO

- [x] Boot and install with VMware
- [ ] Boot and install with VirtualBox
- [ ] Add a vagrant post-processor
- [ ] Add vmware tools so local folders can be mounted
